---
title: "Siemens Siveillance Video Camera"
date: 2025-01-17
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

As of January 10, 2023, CISA will no longer be updating ICS security advisories for Siemens product vulnerabilities beyond the initial advisory. For the most up-to-date information on vulnerabilities in this advisory, please see Siemens' ProductCERT Security Advisories (CERT Services | Services | Siemens Global).

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 5.2**
- **ATTENTION**: Exploitable locally
- **Vendor**: Siemens
- **Equipment**: Siveillance Video Camera Drivers
- **Vulnerability**: Insertion of Sensitive Information into Log File

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow a local attacker to read camera credentials stored in the Recording Server under specific conditions.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Siemens reports that the following products are affected:

- Siveillance Video Device Pack: Versions prior to V13.5

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **INSERTION OF SENSITIVE INFORMATION INTO LOG FILE CWE-532**

Disclosure of sensitive information in HikVision camera driver's log file in XProtect Device Pack allows an attacker to read camera credentials stored in the Recording Server under specific conditions.

CVE-2024-12569 has been assigned to this vulnerability. A CVSS v3 base score of 7.8 has been assigned; the CVSS vector string is (CVSS:3.1/AV:L/AC:H/PR:L/UI:N/S:C/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2024-12569. A base score of 5.2 has been calculated; the CVSS vector string is (CVSS:4.0/AV:L/AC:L/AT:P/PR:L/UI:N/VC:N/VI:N/VA:N/SC:H/SI:H/SA:H).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Commercial Facilities, Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Germany

### 3.4 RESEARCHER

Siemens ProductCERT reported this vulnerability to CISA.

## 4\. MITIGATIONS

Siemens has identified the following specific workarounds and mitigations users can apply to reduce risk:

- Ensure that only trusted people get local access to the driver log files on the Recording Server.
- Update to V13.5 or later version.

As a general security measure, Siemens recommends protecting network access to devices with appropriate mechanisms. To operate the devices in a protected IT environment, Siemens recommends configuring the environment according to Siemens' operational guidelines for industrial security and following recommendations in the product manuals.

Additional information on industrial security by Siemens can be found on the Siemens industrial security webpage

For more information see the associated Siemens security advisory SSA-404759 in HTML and CSAF.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs). Recognize VPNs may have vulnerabilities, should be updated to the most recent version available, and are only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time. This vulnerability is not exploitable remotely. This vulnerability has a high attack complexity.

## 5\. UPDATE HISTORY

- January 16, 2025: Initial Publication

Go to Source
