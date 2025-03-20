---
title: "Hitachi Energy FOX61x Products"
date: 2025-01-17
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v3 4.9**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Hitachi Energy
- **Equipment**: FOX61x Products
- **Vulnerability**: Relative Path Traversal

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an attacker to traverse the file system to access files or directories that would otherwise be inaccessible.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Hitachi Energy reports the following products are affected:

- Hitachi Energy FOX61x: R15A and prior
- Hitachi Energy FOX61x: R15B
- Hitachi Energy FOX61x: R16A
- Hitachi Energy FOX61x: R16B Revision E

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **RELATIVE PATH TRAVERSAL CWE-23**

Hitachi Energy is aware of a vulnerability that affects the FOX61x. If exploited an attacker could traverse the file system to access files or directories that would otherwise be inaccessible.

CVE-2024-2461 has been assigned to this vulnerability. A CVSS v3 base score of 4.9 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:H/UI:N/S:U/C:N/I:H/A:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Switzerland

### 3.4 RESEARCHER

Hitachi Energy PSIRT reported this vulnerability to CISA.

## 4\. MITIGATIONS

Hitachi Energy has identified the following specific workarounds and mitigations users can apply to reduce risk:

- FOX61x R16B Revision E (cesm3\_r16b04\_02, cesne\_r16b04\_02 and f10ne\_r16b04\_02) and older: Update to FOX61x R16B Revision G, Version (cesm3\_r16b04\_07, cesne\_r16b04\_07, f10ne\_r16b04\_07) and apply general mitigation factors. (Hitachi Energy recommends that users apply the update at the earliest convenience).
- FOX61x R15B: Recommended to update to FOX61X R16B Revision G, (cesm3\_r16b04\_07, cesne\_r16b04\_07, f10ne\_r16b04\_07) and apply general mitigation factors.
- FOX61x R15A and older including all subversions, FOX61x R16A: EOL versions - no remediation will be available. Recommended to update to FOX61X R16B Revision G, (cesm3\_r16b04\_07, cesne\_r16b04\_07, f10ne\_r16b04\_07) and apply general mitigation factors.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the Internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs). Recognize VPNs may have vulnerabilities, should be updated to the most recent version available, and are only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

CISA also recommends users take the following measures to protect themselves from social engineering attacks:

- Do not click web links or open attachments in unsolicited email messages.
- Refer to Recognizing and Avoiding Email Scams for more information on avoiding email scams.
- Refer to Avoiding Social Engineering and Phishing Attacks for more information on social engineering attacks.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- January 16, 2025: Initial Publication

Go to Source
