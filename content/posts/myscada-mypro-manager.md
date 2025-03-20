---
title: "mySCADA myPRO Manager"
date: 2025-01-23
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 9.3**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: mySCADA
- **Equipment**: myPRO
- **Vulnerabilities**: Improper Neutralization of Special Elements used in an OS Command ('OS Command Injection')

## 2\. RISK EVALUATION

Successful exploitation of these vulnerabilities could allow a remote attacker to execute arbitrary commands or disclose sensitive information.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following mySCADA products are affected:

- myPRO Manager: Versions prior to 1.3
- myPRO Runtime: Versions prior to 9.2.1

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **Improper Neutralization of Special Elements used in an OS Command ('OS Command Injection') CWE-78**

mySCADA myPRO does not properly neutralize POST requests sent to a specific port with email information. This vulnerability could be exploited by an attacker to execute arbitrary commands on the affected system.

CVE-2025-20061 has been assigned to this vulnerability. A CVSS v3.1 base score of 9.8 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2025-20061. A base score of 9.3 has been calculated; the CVSS vector string is (CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

#### **3.2.2** **Improper Neutralization of Special Elements used in an OS Command ('OS Command Injection') CWE-78**

mySCADA myPRO does not properly neutralize POST requests sent to a specific port with version information. This vulnerability could be exploited by an attacker to execute arbitrary commands on the affected system.

CVE-2025-20014 has been assigned to this vulnerability. A CVSS v3.1 base score of 9.8 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2025-20014. A base score of 9.3 has been calculated; the CVSS vector string is (CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Czech Republic

### 3.4 RESEARCHER

Mehmet INCE (@mdisec) from PRODAFT.com working with Trend Micro Zero Day Initiative reported these vulnerabilities to CISA.

## 4\. MITIGATIONS

mySCADA recommends updating to the latest versions:

- mySCADA PRO Manager 1.3
- mySCADA PRO Runtime 9.2.1

CISA recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs), recognizing VPNs may have vulnerabilities and should be updated to the most current version available. Also recognize VPN is only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- January 23, 2025: Initial Publication

Go to Source
