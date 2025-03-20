---
title: "Sign in as anyone: Bypassing SAML SSO authentication with parser differentials"
date: 2025-03-19
tags: 
  - "development"
  - "git"
  - "github"
  - "gitlab"
  - "software"
---

Critical authentication bypass vulnerabilities (CVE-2025-25291 + CVE-2025-25292) were discovered in ruby-saml up to version 1.17.0. In this blog post, we'll shed light on how these vulnerabilities that rely on a parser differential were uncovered.

The post Sign in as anyone: Bypassing SAML SSO authentication with parser differentials appeared first on The GitHub Blog.

> Critical authentication bypass vulnerabilities (CVE-2025-25291 + CVE-2025-25292) were discovered in ruby-saml up to version 1.17.0. Attackers who are in possession of a single valid signature that was created with the key used to validate SAML responses or assertions of the targeted organization can use it to construct SAML assertions themselves and are in turn able to log in as any user. In other words, it could be used for an account takeover attack. Users of ruby-saml should update to version 1.18.0. References to libraries making use of ruby-saml (such as omniauth-saml) need also be updated to a version that reference a fixed version of ruby-saml.

In this blog post, we detail newly discovered authentication bypass vulnerabilities in the ruby-saml library used for single sign-on (SSO) via SAML on the service provider (application) side. GitHub doesn’t currently use ruby-saml for authentication, but began evaluating the use of the library with the intention of using an open source library for SAML authentication once more. This library is, however, used in other popular projects and products. We discovered an exploitable instance of this vulnerability in GitLab, and have notified their security team so they can take necessary actions to protect their users against potential attacks.

GitHub previously used the ruby-saml library up to 2014, but moved to our own SAML implementation due to missing features in ruby-saml at that time. Following bug bounty reports around vulnerabilities in our own implementation (such as CVE-2024-9487, related to encrypted assertions), GitHub recently decided to explore the use of ruby-saml again. Then in October 2024, a blockbuster vulnerability dropped: an authentication bypass in ruby-saml (CVE-2024-45409) by ahacker1. With tangible evidence of exploitable attack surface, GitHub’s switch to ruby-saml had to be evaluated more thoroughly now. As such, GitHub started a private bug bounty engagement to evaluate the security of the ruby-saml library. We gave selected bug bounty researchers access to GitHub test environments using ruby-saml for SAML authentication. In tandem, the GitHub Security Lab also reviewed the attack surface of the ruby-saml library.

As is not uncommon when multiple researchers are looking at the same code, both ahacker1, a participant in the GitHub bug bounty program, and I noticed the same thing during code review: ruby-saml was using two different XML parsers during the code path of signature verification. Namely, REXML and Nokogiri. While REXML is an XML parser implemented in pure Ruby, Nokogiri provides an easy-to-use wrapper API around different libraries like libxml2, libgumbo and Xerces (used for JRuby). Nokogiri supports parsing of XML and HTML. It looks like Nokogiri was added to ruby-saml to support canonicalization and potentially other things REXML didn’t support at that time.

We both inspected the same code path in the `validate_signature` of `xml_security.rb` and found that the signature element to be verified is first read via REXML, and then also with Nokogiri’s XML parser. So, if REXML and Nokogiri could be tricked into retrieving different signature elements for the same XPath query it might be possible to trick ruby-saml into verifying the wrong signature. It looked like there could be a potential authentication bypass due to a **parser differential**!

The reality was actually more complicated than this.

**Parser differentials** occur when different parsers interpret the same input in different ways. There are other documented samples of parser differentials while parsing XML that led to a security impact:

- “XMPP Stanza Smuggling or How I Hacked Zoom” by Ivan Fratric
- “Psychic paper” by Siguza

But parser differentials are far more common than that and in no way limited to file formats. Other kinds of vulnerabilities often have a parser differential at their core. For example, how URLs are parsed in certain server-side request forgery (SSRF) vulnerabilities or how HTTP headers are interpreted in request smuggling attacks.

The LangSec paper “A Survey of Parser Differential Anti-Patterns” by Ali and Smith categorizes real world parser differentials with regards to their root causes.

Roughly speaking, four stages were involved in the discovery of this authentication bypass:

1. Discovering that two different XML parsers are used during code review.
2. Establishing if and how a parser differential could be exploited.
3. Finding an actual parser differential for the parsers in use.
4. Leveraging the parser differential to create a full-blown exploit.

To prove the security impact of this vulnerability, it was necessary to complete all four stages and create a full-blown authentication bypass exploit.

## Quick recap: how SAML responses are validated

Security assertion markup language (SAML) responses are used to transport information about a signed-in user from the identity provider (IdP) to the service provider (SP) in XML format. Often the only important information transported is a username or an email address. When the HTTP POST binding is used, the SAML response travels from the IdP to the SP via the browser of the end user. This makes it obvious why there has to be some sort of signature verification in play to prevent the user from tampering with the message.

Let’s have a quick look at what a simplified SAML response looks like:  
![A diagram depicting a simplified SAML response on the left and the verification of the digest and the signature on the right.](https://github.blog/wp-content/uploads/2025/03/goodassertion7_2.png?resize=1024%2C355)

_Note: in the response above the XML namespaces were removed for better readability._

As you might have noticed: the main part of a simple SAML response is its assertion element (A), whereas the main information contained in the assertion is the information contained in the `Subject` element (B) (here the NameID containing the username: admin). A real assertion typically contains more information (e.g. `NotBefore` and `NotOnOrAfter` dates as part of a `Conditions` element.)

Normally, the `Assertion` (A) (without the whole `Signature` part) is canonicalized and then compared against the `DigestValue` (C) and the `SignedInfo` (D) is canonicalized and verified against the `SignatureValue` (E). In this sample, the assertion of the SAML response is signed, and in other cases the whole SAML response is signed.

## Searching for parser differentials

We learned that ruby-saml used two different XML parsers (REXML and Nokogiri) for validating the SAML response. Now let’s have a look at the verification of the signature and the digest comparison.  
The focus of the following explanation lies on the `validate_signature` method inside of `xml_security.rb`.

Inside that method, there’s a broad XPath query with REXML for the first signature element inside the SAML document:

```plaintext
sig_element = REXML::XPath.first(
  @working_copy,
  "//ds:Signature",
  {"ds"=>DSIG}
)
```

_Hint: When reading the code snippets, you can tell the difference between queries for REXML and Nokogiri by looking at how they are called. REXML methods are prefixed with `REXML::`, whereas Nokogiri methods are called on `document`._

Later, the actual `SignatureValue` is read from this element:

```plaintext
base64_signature = REXML::XPath.first(
  sig_element,
  "./ds:SignatureValue",
  {"ds" => DSIG}
)
signature = Base64.decode64(OneLogin::RubySaml::Utils.element_text(base64_signature))
```

Note: the name of the `Signature` element might be a bit confusing. While it contains the actual signature in the `SignatureValue` node it also contains the part that is actually signed in the `SignedInfo` node. Most importantly the `DigestValue` element contains the digest (hash) of the assertion and information about the used key.

So, an actual `Signature` element could look like this (removed namespace information for better readability):

```plaintext
<Signature>
    <SignedInfo>
        <CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#" />
        <SignatureMethod Algorithm="http://www.w3.org/2001/04/xmldsig-more#rsa-sha256" />
        <Reference URI="#_SAMEID">
            <Transforms><Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#" /></Transforms>
            <DigestMethod Algorithm="http://www.w3.org/2001/04/xmlenc#sha256" />
            <DigestValue>Su4v[..]</DigestValue>
        </Reference>
    </SignedInfo>
    <SignatureValue>L8/i[..]</SignatureValue>
    <KeyInfo>
        <X509Data>
            <X509Certificate>MIID[..]</X509Certificate>
        </X509Data>
    </KeyInfo>
</Signature>
```

Later in the same method (`validate_signature`) there’s again a query for the Signature(s)—but this time with Nokogiri.

```plaintext
noko_sig_element = document.at_xpath('//ds:Signature', 'ds' => DSIG)
```

Then the `SignedInfo` element is taken from that signature and canonicalized:

```plaintext
noko_signed_info_element = noko_sig_element.at_xpath('./ds:SignedInfo', 'ds' => DSIG)

canon_string = noko_signed_info_element.canonicalize(canon_algorithm)
```

Let’s remember this `canon_string` contains the canonicalized `SignedInfo` element.

The `SignedInfo` element is then also extracted with REXML:

```plaintext
 signed_info_element = REXML::XPath.first(
        sig_element,
        "./ds:SignedInfo",
        { "ds" => DSIG }
 )
```

From this `SignedInfo` element the `Reference` node is read:

```plaintext
ref = REXML::XPath.first(signed_info_element, "./ds:Reference", {"ds"=>DSIG})
```

Now the code queries for the referenced node by looking for nodes with the signed element id using Nokogiri:

```plaintext
reference_nodes = document.xpath("//*[@ID=$id]", nil, { 'id' => extract_signed_element_id })
```

The method `extract_signed_element_id` extracts the signed element id with help of REXML. From the previous authentication bypass (CVE-2024-45409), there’s now a check that only one element with the same ID can exist.

The first of the `reference_nodes` is taken and canonicalized:

```plaintext
hashed_element = reference_nodes[0][..]canon_hashed_element = hashed_element.canonicalize(canon_algorithm, inclusive_namespaces)
```

The `canon_hashed_element` is then hashed:

```plaintext
hash = digest_algorithm.digest(canon_hashed_element)
```

The `DigestValue` to compare it against is then extracted with REXML:

```plaintext
encoded_digest_value = REXML::XPath.first(
        ref,
        "./ds:DigestValue",
        { "ds" => DSIG }
      )
digest_value = Base64.decode64(OneLogin::RubySaml::Utils.element_text(encoded_digest_value))
```

Finally, the `hash` (built from the element extracted by Nokogiri) is compared against the `digest_value` (extracted with REXML):

```plaintext
unless digests_match?(hash, digest_value)
```

The `canon_string` extracted some lines ago (a result of an extraction with Nokogiri) is later verified against `signature` (extracted with REXML).

```plaintext
unless cert.public_key.verify(signature_algorithm.new, signature, canon_string)
```

In the end, we have the following constellation:

1. The assertion is extracted and canonicalized with Nokogiri, and then hashed. In contrast, the hash against which it will be compared is extracted with REXML.
2. The SignedInfo element is extracted and canonicalized with Nokogiri - it is then verified against the SignatureValue, which was extracted with REXML.

## Exploiting the parser differential

The question is: is it possible to create an XML document where REXML sees one signature and Nokogiri sees another?

It turns out, yes.

Ahacker1, participating in the bug bounty, was faster to produce a working exploit using a parser differential. Among other things, ahacker1 was inspired by the XML roundtrips vulnerabilities published by Mattermost’s Juho Forsén in 2021.

Not much later, I produced an exploit using a different parser differential with the help of Trail of Bits’ Ruby fuzzer called ruzzy.

Both exploits result in an authentication bypass. Meaning that an attacker, who is in possession of a single valid signature that was created with the key used to validate SAML responses or assertions of the targeted organization, can use it to construct assertions for any users which will be accepted by ruby-saml. Such a signature can either come from a signed assertion or response from another (unprivileged) user or in certain cases, it can even come from signed metadata of a SAML identity provider (which can be publicly accessible).

An exploit could look like this. Here, an additional Signature was added as part of the `StatusDetail` element that is only visible to Nokogiri:

![A diagram depicting a simplified SAML response on the left and the verification of the digest and the signature on the right. For both the signature and the digest verification one part is extracted using Nokogiri and the other using REXML.](https://github.blog/wp-content/uploads/2025/03/rubysaml-parser-diff-simplified8_2.png?resize=1024%2C400)

In summary:

The `SignedInfo` element (A) from the signature that is visible to Nokogiri is canonicalized and verified against the `SignatureValue` (B) that was extracted from the signature seen by REXML.

The assertion is retrieved via Nokogiri by looking for its ID. This assertion is then canonicalized and hashed (C). The hash is then compared to the hash contained in the `DigestValue` (D). This DigestValue was retrieved via REXML. This DigestValue has no corresponding signature.

So, two things take place:

- A valid SignedInfo with DigestValue is verified against a valid signature. (which checks out)
- A fabricated canonicalized assertion is compared against its calculated digest. (which checks out as well)

This allows an attacker, who is in possession of a valid signed assertion for any (unprivileged) user, to fabricate assertions and as such impersonate any other user.

### Check for errors when using Nokogiri

Parts of the currently known, undisclosed exploits can be stopped by checking for Nokogiri parsing errors on SAML responses. Sadly, those errors do not result in exceptions, but need to be checked on the `errors` member of the parsed document:

```plaintext
doc = Nokogiri::XML(xml) do |config|
  config.options = Nokogiri::XML::ParseOptions::STRICT | Nokogiri::XML::ParseOptions::NONET
end

raise "XML errors when parsing: " + doc.errors.to_s if doc.errors.any?
```

While this is far from a perfect fix for the issues at hand, it renders at least one exploit infeasible.

## Indicators of compromise

We are not aware of any reliable indicators of compromise. While we’ve found a potential indicator of compromise, it only works in debug-like environments and to publish it, we would have to reveal too many details about how to implement a working exploit so we’ve decided that it’s better not to publish it. Instead, our best recommendation is to look for suspicious logins via SAML on the service provider side from IP addresses that do not align with the user’s expected location.

## SAML and XML signatures:as confusing as it gets

Some might say it’s hard to integrate systems with SAML. That might be true. However, it’s even harder to write implementations of SAML using XML signatures in a secure way. As others have stated before: it’s probably best to disregard the specifications, as following them doesn’t help build secure implementations.  
To rehash how the validation works if the SAML assertion is signed, let’s have a look at the graphic below, depicting a simplified SAML response. The assertion, which transports the protected information, contains a signature. Confusing, right?

![A diagram showing a SAML response and its parts: the Assertion containing the Signature and the Signature containing the SignedInfo of which the DigestValue is a part.](https://github.blog/wp-content/uploads/2025/03/conclusion-combined-saml.png?resize=1024%2C497)

To complicate it even more: What is even signed here? The whole assertion? No!

What’s signed is the `SignedInfo` element and the `SignedInfo` element contains a `DigestValue`. This `DigestValue` is the hash of the canonicalized assertion with the signature element removed before the canonicalization. This two-stage verification process can lead to implementations that have a disconnect between the verification of the hash and the verification of the signature. This is the case for these Ruby-SAML parser differentials: while the hash and the signature check out on their own, they have no connection. The hash is actually a hash of the assertion, but the signature is a signature of a different `SignedInfo` element containing another hash. What you actually want is a direct connection between the hashed content, the hash, and the signature. (And once the verification is done you only want to retrieve information from the exact part that was actually verified.) Or, alternatively, use a less complicated standard to transport a cryptographically signed username between two systems - but here we are.

In this case, the library already extracted the `SignedInfo` and used it to verify the signature of its canonicalized string,`canon_string`. However, it did not use it to obtain the digest value. If the library had used the content of the already extracted `SignedInfo` to obtain the digest value, it would have been secure in this case even with two XML parsers in use.

## Conclusion

As shown once again: relying on two different parsers in a security context can be tricky and error-prone. That being said: exploitability is not automatically guaranteed in such cases. As we have seen in this case, checking for Nokogiri errors could not have prevented the parser differential, but could have stopped at least one practical exploitation of it.

The initial fix for the authentication bypasses does not remove one of the XML parsers to prevent API compatibility problems. As noted, the more fundamental issue was the disconnect between verification of the hash and verification of the signature, which was exploitable via parser differentials. The removal of one of the XML parsers was already planned for other reasons, and will likely come as part of a major release in combination with additional improvements to strengthen the library. If your company relies on open source software for business-critical functionality, consider sponsoring them to help fund their future development and bug fix releases.

If you’re a user of ruby-saml library, make sure to update to the latest version, 1.18.0, containing fixes for CVE-2025-25291 and CVE-2025-25292. References to libraries making use of ruby-saml (such as omniauth-saml) need also be updated to a version that reference a fixed version of ruby-saml. We will publish a proof of concept exploit at a later date in the GitHub Security Lab repository.

### Acknowledgments

Special thanks to Sixto Martín, maintainer of ruby-saml, and Jeff Guerra from the GitHub Bug Bounty program.  
Special thanks also to ahacker1 for giving inputs to this blog post.

### Timeline

- 2024-11-04: Bug bounty report demonstrating an authentication bypass was reported against a GitHub test environment evaluating ruby-saml for SAML authentication.
- 2024-11-04: Work started to identify and test potential mitigations.
- 2024-11-12: A second authentication bypass was found by Peter that renders the planned mitigations for the first useless.
- 2024-11-13: Initial contact with Sixto Martín, maintainer of ruby-saml.
- 2024-11-14: Both parser differentials are reported to ruby-saml, the maintainer responds immediately.
- 2024-11-14: The work on potential patches by the maintainer and ahacker1 begins. (One of the initial ideas was to remove one of the XML parsers, but this was not feasible without breaking backwards compatibility).
- 2025-02-04: ahacker1 proposes a non-backwards compatible fix.
- 2025-02-06: ahacker1 also proposes a backwards compatible fix.
- 2025-02-12: The 90 days deadline of GitHub Security Lab advisories ends.
- 2025-02-16: The maintainer starts working on a fix with the idea to be backwards-compatible and easier to understand.
- 2025-02-17: Initial contact with GitLab to coordinate a release of their on-prem product with the release of the ruby-saml library.
- 2025-03-12: A fixed version of ruby-saml was released.

The post Sign in as anyone: Bypassing SAML SSO authentication with parser differentials appeared first on The GitHub Blog.

Go to Source
