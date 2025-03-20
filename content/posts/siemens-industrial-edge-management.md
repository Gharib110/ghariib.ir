---
title: "Siemens Industrial Edge Management"
date: 2025-01-17
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

As of January 10, 2023, CISA will no longer be updating ICS security advisories for Siemens product vulnerabilities beyond the initial advisory. For the most up-to-date information on vulnerabilities in this advisory, please see Siemens' ProductCERT Security Advisories (CERT Services | Services | Siemens Global).

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 2.1**
- **ATTENTION**: Exploitable remotely
- **Vendor**: Siemens
- **Equipment**: Industrial Edge Management
- **Vulnerability**: Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an attacker to extract sensitive information by tricking users into accessing a malicious link.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Siemens reports that the following products are affected:

- Siemens Industrial Edge Management OS (IEM-OS): All versions

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **IMPROPER NEUTRALIZATION OF INPUT DURING WEB PAGE GENERATION ('CROSS-SITE SCRIPTING') CWE-79**

Affected components are vulnerable to reflected cross-site scripting (XSS) attacks. This could allow an attacker to extract sensitive information by tricking users into accessing a malicious link.

CVE-2024-45385 has been assigned to this vulnerability. A CVSS v3 base score of 4.7 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:H/PR:N/UI:R/S:C/C:L/I:L/A:N).

A CVSS v4 score has also been calculated for CVE-2024-45385. A base score of 2.1 has been calculated; the CVSS vector string is (AV:N/AC:H/AT:N/PR:N/UI:A/VC:N/VI:N/VA:N/SC:L/SI:L/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Energy
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Germany

### 3.4 RESEARCHER

Siemens ProductCERT reported this vulnerability to CISA.

## 4\. MITIGATIONS

Siemens has identified the following specific workarounds and mitigations users can apply to reduce risk:

- Industrial Edge Management OS (IEM-OS): Currently no fix is planned. Migrate to Industrial Edge Management Virtual (IEM-V)

As a general security measure, Siemens recommends protecting network access to devices with appropriate mechanisms. To operate the devices in a protected IT environment, Siemens recommends configuring the environment according to Siemens' operational guidelines for industrial security and following recommendations in the product manuals.

Additional information on industrial security by Siemens can be found on the Siemens industrial security webpage.

For more information see the associated Siemens security advisory SSA-416411 in HTML and CSAF.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet.
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

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time. This vulnerability has a high attack complexity.

## 5\. UPDATE HISTORY

- January 16, 2025: Initial Publication

Go to Source
