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

- **CVSS v4 7.0**
- **ATTENTION**: Low attack complexity
- **Vendor**: Rockwell Automation
- **Equipment**: FactoryTalk
- **Vulnerabilities**: Incorrect Permission Assignment for Critical Resource, Improper Control of Generation of Code ('Code Injection')

## 2\. RISK EVALUATION

Successful exploitation of these vulnerabilities could allow an attacker to gain unauthenticated access to system configuration files and execute DLLs with elevated privileges.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following versions of Rockwell Automation Factory Talk are affected:

- FactoryTalk: All versions prior to 15.0
- FactoryTalk View SE: All versions prior to 15.0

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **Incorrect Permission Assignment for Critical Resource CWE-732**

An incorrect permission assignment vulnerability exists in Rockwell Automation FactoryTalk products on all versions prior to Version 15.0. The vulnerability is due to incorrect permissions being assigned to the remote debugger port and can allow for unauthenticated access to the system configuration.

CVE-2025-24481 has been assigned to this vulnerability. A CVSS v3.1 base score of 7.3 has been calculated; the CVSS vector string is (AV:L/AC:L/PR:N/UI:N/S:U/C:L/I:L/A:H).

A CVSS v4 score has also been calculated for CVE-2025-24481. A base score of 7.0 has been calculated; the CVSS vector string is (AV:L/AC:L/AT:N/PR:N/UI:N/VC:L/VI:L/VA:H/SC:N/SI:N/SA:N).

#### **3.2.2** **Improper Control of Generation of Code ('Code Injection') CWE-94**

A local code injection vulnerability exists in Rockwell Automation FactoryTalk View SE products on all versions prior to Version 15.0. The vulnerability is due to incorrect default permissions and allows for DLLs to be executed with higher level permissions.

CVE-2025-24482 has been assigned to this vulnerability. A CVSS v3.1 base score of 7.3 has been calculated; the CVSS vector string is (AV:L/AC:L/PR:N/UI:N/S:U/C:L/I:L/A:H).

A CVSS v4 score has also been calculated for CVE-2025-24482. A base score of 7.0 has been calculated; the CVSS vector string is (AV:L/AC:L/AT:N/PR:N/UI:N/VC:L/VI:L/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** United States

### 3.4 RESEARCHER

Rockwell Automation reported these vulnerabilities to CISA.

## 4\. MITIGATIONS

Rockwell Automation encourages users of the affected software to apply the following risk mitigations, if possible:

- For 11470:
    - Upgrade to V15.0 or apply patch. Answer ID 1152306
    - Protect physical access to the workstation
    - Restrict access to Port 8091 at the network or workstation
- For 11508:
    - Upgrade to V15.0 or apply patch. Answer ID 1152304.
    - Check the environment variables (PATH), and make sure FactoryTalk® View SE installation path (C:Program Files (x86)Common FilesRockwell) is before all others

For information on how to mitigate Security Risks on industrial automation control systems, Rockwell Automation asks users to implement their suggested security best practices to minimize the risk of the vulnerabilities.

Users can use Stakeholder-Specific Vulnerability Categorization to generate more environment-specific prioritization.

CISA recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the Internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs), recognizing VPNs may have vulnerabilities and should be updated to the most current version available. Also recognize VPN is only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time. These vulnerabilities were not exploitable remotely.

## 5\. UPDATE HISTORY

- January 28, 2025: Initial Publication

Go to Source
