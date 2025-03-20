---
title: "Rockwell Automation FactoryTalk AssetCentre"
date: 2025-02-06
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 9.3**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Rockwell Automation
- **Equipment**: FactoryTalk AssetCentre
- **Vulnerabilities**: Inadequate Encryption Strength, Insufficiently Protected Credentials

## 2\. RISK EVALUATION

Successful exploitation of these vulnerabilities could allow an attacker to extract passwords, access, credentials, or impersonate other users.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following versions of Rockwell Automation FactoryTalk AssetCentre are affected:

- FactoryTalk AssetCentre: All versions prior to V15.00.001

### 3.2 Vulnerability Overview

#### **3.2.1** **INADEQUATE ENCRYPTION STRENGTH CWE-326**

An encryption vulnerability exists in all versions prior to V15.00.001 of FactoryTalk AssetCentre. The vulnerability exists due to a weak encryption methodology and could allow a threat actor to extract passwords belonging to other users of the application.

CVE-2025-0477 has been assigned to this vulnerability. A CVSS v3.1 base score of 9.8 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2025-0477. A base score of 9.3 has been calculated; the CVSS vector string is (AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

#### **3.2.2** **INSUFFICIENTLY PROTECTED CREDENTIALS CWE-522**

A data exposure vulnerability exists in all versions prior to V15.00.001 of FactoryTalk AssetCentre. The vulnerability exists due to storing credentials in the configuration file of EventLogAttachmentExtractor, ArchiveExtractor, LogCleanUp, or ArchiveLogCleanUp packages.

CVE-2025-0497 has been assigned to this vulnerability. A CVSS v3.1 base score of 7.0 has been calculated; the CVSS vector string is (AV:L/AC:H/PR:L/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2025-0497. A base score of 7.3 has been calculated; the CVSS vector string is (AV:L/AC:H/AT:N/PR:L/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

#### **3.2.3** **INSUFFICIENTLY PROTECTED CREDENTIALS CWE-522**

A data exposure vulnerability exists in all versions prior to V15.00.001 of FactoryTalk AssetCentre. The vulnerability exists due to insecure storage of FactoryTalk Security user tokens which could allow a threat actor to steal a token and, impersonate another user.

CVE-2025-0498 has been assigned to this vulnerability. A CVSS v3.1 base score of 7.8 has been calculated; the CVSS vector string is (AV:L/AC:L/PR:N/UI:R/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2025-0498. A base score of 7.0 has been calculated; the CVSS vector string is (AV:L/AC:L/AT:N/PR:L/UI:P/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** United States

### 3.4 RESEARCHER

Nestlé - Alban Avdiji reported these vulnerabilities to Rockwell Automation.

## 4\. MITIGATIONS

Rockwell Automation recommends users follow the following mitigations:

- For CVE-2025-0477: Update FactoryTalk AssetCentre to v15.00.01 or later. The encrypted data is stored in a table in the database. Control access to the database by non-essential users.
- For CVE-2025-0497: Update FactoryTalk AssetCentre to v15.00.01 or later. Apply patches to correct legacy versions: To apply the patch for LogCleanUp or ArchiveLogCleanUp, download and install the Rockwell Automation January 2025 monthly patch rollup, or later. To apply patches for EventLogAttachmentExtractor or ArchiveExtractor, locate the article BF31148, download the patch files and follow the instructions. Restrict physical access to the machine to authorized users.
- For CVE-2025-0498: Update FactoryTalk AssetCentre to v15.00.01 or later. Apply patches to correct legacy versions: To apply the patch for download and install the Rockwell Automation January 2025 monthly patch rollup, or later. Restrict physical access to the machine to authorized users.

For information on how to mitigate security risks on industrial automation control systems, Rockwell Automation encourages users to implement their suggested security best practices to minimize the risk of the vulnerability.

For more information about this issue, please see the advisory on the Rockwell Automation security page.

CISA recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities, such as:

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

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- January 30, 2025: Initial Publication

Go to Source
