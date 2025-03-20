---
title: "Rockwell Automation DataMosaix Private Cloud"
date: 2025-01-29
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
- **Equipment**: DataMosaix Private Cloud
- **Vulnerabilities**: Exposure of Sensitive Information to an Unauthorized Actor, Dependency on Vulnerable Third-Party Component

## 2\. RISK EVALUATION

Successful exploitation of these vulnerabilities could overwrite reports, including user projects.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Rockwell Automation reports the following versions of DataMosaix Private Cloud are affected:

- DataEdgePlatform DataMosaix Private Cloud: Version 7.11 and prior (CVE-2025-0659)
- DataEdgePlatform DataMosaix Private Cloud: Versions 7.09 and prior (CVE-2020-11656)

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **Exposure of Sensitive Information to an Unauthorized Actor CWE-200**

A path traversal vulnerability exists in DataMosaix Private Cloud. By specifying the character sequence in the body of the vulnerable endpoint, it is possible to overwrite files outside of the intended directory. A threat actor with admin privileges could leverage this vulnerability to overwrite reports including user projects.

CVE-2024-11932 has been assigned to this vulnerability. A CVSS v3.1 base score of 5.5 has been calculated; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:H/UI:N/S:U/C:L/I:H/A:N).

A CVSS v4 score has also been calculated for CVE-2024-11932. A base score of 7.0 has been calculated; the CVSS vector string is (CVSS:4.0/AV:N/AC:L/AT:N/PR:H/UI:N/VC:L/VI:H/VA:N/SC:N/SI:N/SA:N).

#### **3.2.2** **Dependency on Vulnerable Third-Party Component CWE-1395**

DataMosaix Private Cloud utilizes SQLite, which contains a use after free vulnerability in the ALTER TABLE implementation, which was demonstrated by an ORDER BY clause that belongs to a compound SELECT statement.

CVE-2020-11656 has been assigned to this vulnerability. A CVSS v3.1 base score of 9.8 has been calculated; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2020-11656. A base score of 9.3 has been calculated; the CVSS vector string is (CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** United States

### 3.4 RESEARCHER

Rockwell Automation reported these vulnerabilities to CISA.

## 4\. MITIGATIONS

Rockwell Automation has addressed these issues in version v7.11.01 and encourages users to update to the newest available version. Rockwell Automation encourages users to mitigate security risks on industrial automation control systems by implement their suggested security best practices, where possible.   

For more information about this issue, please see the advisory on the Rockwell Automation security page.

CISA recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the Internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as virtual private networks (VPNs), recognizing VPNs may have vulnerabilities and should be updated to the most current version available. Also recognize VPN is only as secure as the connected devices.

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

- January 28, 2025: Initial Publication

Go to Source
