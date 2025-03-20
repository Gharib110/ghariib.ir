---
title: "ZF Roll Stability Support Plus (RSSPlus)"
date: 2025-01-22
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 5.9**
- **ATTENTION**: Exploitable from an adjacent network/low attack complexity
- **Vendor**: ZF
- **Equipment**: RSSPlus
- **Vulnerability**: Authentication Bypass By Primary Weakness

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an unauthenticated attacker to remotely (proximal/adjacent with RF equipment) call diagnostic functions which could impact both the availability and integrity.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following versions of RSSPlus are affected:

- RSSPlus 2M: build dates 01/08 through at least 01/23

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **AUTHENTICATION BYPASS BY PRIMARY WEAKNESS CWE-305**

The affected product is vulnerable to an authentication bypass vulnerability targeting deterministic RSSPlus SecurityAccess service seeds, which may allow an attacker to remotely (proximal/adjacent with RF equipment or via pivot from J2497 telematics devices) call diagnostic functions intended for workshop or repair scenarios. This can impact system availability, potentially degrading performance or erasing software, however the vehicle remains in a safe vehicle state.

CVE-2024-12054 has been assigned to this vulnerability. A CVSS v3.1 base score of 5.4 has been calculated; the CVSS vector string is (AV:A/AC:H/PR:N/UI:R/S:U/C:N/I:L/A:H).

A CVSS v4 score has also been calculated for CVE-2024-12054. A base score of 5.9 has been calculated; the CVSS vector string is (CVSS:4.0/AV:A/AC:H/AT:P/PR:N/UI:P/VC:N/VI:L/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Transportation Systems
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Germany

### 3.4 RESEARCHER

National Motor Freight Traffic Association, Inc. (NMFTA) researchers Ben Gardiner and Anne Zachos reported this vulnerability to CISA.

## 4\. MITIGATIONS

To most effectively mitigate general vulnerabilities of the powerline communication, any trucks, trailers, and tractors utilizing J2497 technology should disable all features where possible, except for backwards-compatibility with LAMP ON detection only. Users acquiring new trailer equipment should migrate all diagnostics to newer trailer bus technology. Users acquiring new tractor equipment should remove support for reception of any J2497 message other than LAMP messages.

ZF recommends:

- Moving away from security access and implementing the latest security feature authenticate (0x29)
- Ensure random numbers are generated from a cryptographically secure hardware true random number generator
- Adopting modern standards/protocols for truck trailer communication

NMFTA has published detailed information about how to mitigate these issues in the following ways:

- Install a LAMP ON firewall for each ECU
- Use a LAMP detect circuit LAMP ON sender with each trailer
- Change addresses dynamically on each tractor in response to detecting a transmitter on its current address.
- Install RF chokes on each trailer between chassis ground and wiring ground
- Load with LAMP keyhole signal on each tractor
- Flood with jamming signal on each tractor

Please visit NMFTA for additional details on these and other solutions.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs), recognizing VPNs may have vulnerabilities and should be updated to the most current version available. Also recognize VPN is only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

CISA also recommends users take the following measures to protect themselves from social engineering attacks:

- Do not click web links or open attachments in unsolicited email messages.
- Refer to Recognizing and Avoiding Email Scams for more information on avoiding email scams.
- Refer to Avoiding Social Engineering and Phishing Attacks for more information on social engineering attacks.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- January 21, 2025: Initial Publication

Go to Source
