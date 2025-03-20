---
title: "HMS Networks Ewon Flexy 202"
date: 2025-01-23
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 6.9**
- **ATTENTION**: Low attack complexity
- **Vendor**: HMS Networks
- **Equipment**: Ewon Flexy 202
- **Vulnerability**: Cleartext Transmission of Sensitive Information

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an attacker to disclose sensitive user credentials.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following HMS Networks products are affected:

- Ewon Flexy 202: All versions

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **Cleartext Transmission of Sensitive Information CWE-319**

EWON Flexy 202 transmits user credentials in clear text with no encryption when a user is added, or user credentials are changed via its webpage.

CVE-2025-0432 has been assigned to this vulnerability. A CVSS v3.1 base score of 5.7 has been calculated; the CVSS vector string is (AV:A/AC:L/PR:N/UI:R/S:U/C:H/I:N/A:N).

A CVSS v4 score has also been calculated for CVE-2025-0432. A base score of 6.9 has been calculated; the CVSS vector string is (AV:A/AC:L/AT:N/PR:N/UI:P/VC:H/VI:N/VA:N/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Sweden

### 3.4 RESEARCHER

Khalid Markar, Parul Sindhwad and Dr. Faruk Kazi from CoE-CNDS Lab, VJTI, Mumbai, India reported this vulnerability to CISA

## 4\. MITIGATIONS

To ensure the highest level of security when using the Ewon Flexy device, HMS strongly recommend following these best practices:

- Integrate with Talk2M Cloud: Always use the Flexy device in conjunction with Talk2M cloud. This guarantees a robust security level for your remote access connections.
- Follow the the guidelines outlined here: Best Practices for Secure Usage of the Ewon Solution
- Disable Unused Protocols: Regularly review and disable any unsecure protocols that are not in use. Learn how to do this here: How to Block Unused Ewon Services

For further information, please visit the HMS Security Advisories page.

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

- January 23, 2025: Initial Publication

Go to Source
