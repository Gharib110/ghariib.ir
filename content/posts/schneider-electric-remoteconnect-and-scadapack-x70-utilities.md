---
title: "Schneider Electric RemoteConnect and SCADAPack x70 Utilities"
date: 2025-01-29
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 8.5**
- **ATTENTION**: Low Attack Complexity
- **Vendor**: Schneider Electric
- **Equipment**: Electric RemoteConnect and SCADAPack x70 Utilities
- **Vulnerability**: Deserialization of Untrusted Data

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could lead to loss of confidentiality, integrity, and potential remote code execution on workstation when a non-admin authenticated user opens a malicious project file.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Schneider Electric reports that the following products are affected:

- RemoteConnect: All versions
- SCADAPackTM x70 Utilities: All versions

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **DESERIALIZATION OF UNTRUSTED DATA CWE-502**

A deserialization of untrusted data vulnerability exists that could lead to loss of confidentiality, integrity, and potential remote code execution on workstation when a non-admin authenticated user opens a malicious project file.

CVE-2024-12703 has been assigned to this vulnerability. A CVSS v3 base score of 7.8 has been assigned; the CVSS vector string is (CVSS:3.1/AV:L/AC:L/PR:N/UI:R/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2024-12703. A base score of 8.5 has been calculated; the CVSS vector string is (CVSS:4.0/AV:L/AC:L/AT:N/PR:N/UI:P/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

**CRITICAL INFRASTRUCTURE SECTORS:** Energy, Critical Manufacturing.

- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** France

### 3.4 RESEARCHER

Schneider Electric reported this vulnerability to CISA.

## 4\. MITIGATIONS

Schneider Electric is establishing a remediation plan for all future versions of RemoteConnect and SCADAPackTM x70 Utilities that will include a fix for this vulnerability. Until then, Schneider Electric recommends that users should immediately apply the following mitigations to reduce the risk of exploit:

- Only open project files received from a trusted source.
- Compute a hash of the project files and regularly check the consistency of this hash to verify the integrity before usage.
- Encrypt project file when stored and restrict the access to only trusted users.
- When exchanging files over the network, use secure communication protocols.
- Follow the SCADAPackTM Security Guidelines.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs). Recognize VPNs may have vulnerabilities, should be updated to the most recent version available, and are only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets. Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies. Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

CISA also recommends users take the following measures to protect themselves from social engineering attacks:

- Do not click web links or open attachments in unsolicited email messages.
- Refer to Recognizing and Avoiding Email Scams for more information on avoiding malicious email.
- Refer to Avoiding Social Engineering and Phishing Attacks for more information on social engineering attacks.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time. This vulnerability is not exploitable remotely.

## 5\. UPDATE HISTORY

- January 28, 2025: Initial Publication

Go to Source
