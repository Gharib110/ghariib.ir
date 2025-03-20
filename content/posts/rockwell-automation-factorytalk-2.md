---
title: "Rockwell Automation FactoryTalk"
date: 2025-01-29
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 9.3**
- **ATTENTION**: Low attack complexity
- **Vendor**: Rockwell Automation
- **Equipment**: FactoryTalk
- **Vulnerabilities**: Incorrect Authorization, Improper Neutralization of Special Elements used in an OS Command ('OS Command Injection')

## 2\. RISK EVALUATION

Successful exploitation of these vulnerabilities could allow an attacker to execute code on the device with elevated privileges.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following versions of Rockwell Automation FactoryTalk View ME are affected:

- FactoryTalk View ME: All versions prior to 15.0

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **Incorrect Authorization CWE-863**

A local code execution vulnerability exists in in Rockwell Automation FactoryTalk products on all versions prior to version 15.0. The vulnerability is due to a default setting in Windows and allows access to the command prompt as a higher privileged user.

CVE-2025-24479 has been assigned to this vulnerability. A CVSS v3.1 base score of 8.4 has been calculated; the CVSS vector string is (AV:L/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2025-24479. A base score of 8.6 has been calculated; the CVSS vector string is (AV:L/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

#### **3.2.2** **Improper Neutralization of Special Elements Used in an OS Command ('OS Command Injection') CWE-78**

A remote code execution vulnerability exists in Rockwell Automation FactoryTalk products on all versions prior to version 15.0. The vulnerability is due to lack of input sanitation and could allow a remote attacker to run commands or code as a high privileged user.

CVE-2025-24480 has been assigned to this vulnerability. A CVSS v3.1 base score of 9.8 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2025-24480. A base score of 9.3 has been calculated; the CVSS vector string is (AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** United States

### 3.4 RESEARCHER

Rockwell Automation reported these vulnerabilities to CISA.

## 4\. MITIGATIONS

Rockwell Automation encourages users of the affected software to apply the following risk mitigations, if possible:

- CVE-2025-24479
    - Upgrade to V15.0 or apply patch in AID 1152309
    - Control physical access to the system
- CVE-2025-24480
    - Upgrade to V15.0 or apply patch in AID 1152331, 1152332.
    - Protect network access to the device
    - Strictly constrain the parameters of invoked functions

For information on how to mitigate security risks on industrial automation control systems, Rockwell Automation encourages users to implement their suggested security best practices to minimize the risk of the vulnerability.

Stakeholder-Specific Vulnerability Categorization can be used to generate more environment-specific prioritization.

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

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- January 28, 2025: Initial Publication

Go to Source
