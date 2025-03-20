---
title: "Tibbo AggreGate Network Manager"
date: 2025-01-02
categories: 
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 8.7**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Tibbo
- **Equipment**: AggreGate Network Manager
- **Vulnerability**: Unrestricted Upload of File with Dangerous Type

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an attacker to achieve code execution on the affected device.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following Tibbo products are affected:

- Aggregate Network Manager: Versions 6.34.02 and prior

### 3.2 Vulnerability Overview

#### **3.2.1** **Unrestricted Upload of File with Dangerous Type CWE-434**

There is an unrestricted file upload vulnerability where it is possible for an authenticated user (low privileged) to upload an jsp shell and execute code with the privileges of user running the web server.

CVE-2024-12700 has been assigned to this vulnerability. A CVSS v3.1 base score of 8.8 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2024-12700. A base score of 8.7 has been calculated; the CVSS vector string is (CVSS:4.0/AV:N/AC:L/AT:N/PR:L/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Communications, Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Taiwan

### 3.4 RESEARCHER

Vu Khanh Trinh (@Sonicrr) of VNPT Cyber Immunity working with Trend Micro Zero Day Initiative reported this vulnerability to CISA.

## 4\. MITIGATIONS

Tibbo recommends users update to Versions 6.40.02, 6.34.03, or latest version.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the Internet.
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

- December 19, 2024: Initial Publication
