---
title: "Western Telematic Inc NPS Series, DSM Series, CPM Series"
date: 2025-02-06
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 6.0**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Western Telematic Inc
- **Equipment**: NPS Series, DSM Series, CPM Series
- **Vulnerability**: External Control of File Name or Path

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an authenticated attacker to gain privileged access to files on the device's filesystem.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following Western Telematic Inc products are affected:

- Network Power Switch (NPS Series): Firmware Version 6.62 and prior
- Console Server (DSM Series): Firmware Version 6.62 and prior
- Console Server + PDU Combo Unit (CPM Series): Firmware Version 6.62 and prior

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **External Control of File Name or Path CWE-73**

Multiple Western Telematic (WTI) products contain a web interface that is vulnerable to a Local File Inclusion Attack (LFI), where any authenticated user has privileged access to files on the device's filesystem.

CVE-2025-0630 has been assigned to this vulnerability. A CVSS v3.1 base score of 6.5 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:N/A:N).

A CVSS v4 score has also been calculated for CVE-2025-0630. A base score of 6.0 has been calculated; the CVSS vector string is (AV:N/AC:L/AT:P/PR:L/UI:N/VC:H/VI:N/VA:N/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Communications
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** United States

### 3.4 RESEARCHER

notnotnotveg (notnotnotveg@gmail.com) reported this vulnerability to CISA.

## 4\. MITIGATIONS

Western Telematic Inc reports this issue was discovered and patched in 2020. Western Telematic Inc recommends users follow best practices and update to the latest version.

- For DSM/CPM units: Update to 8.06
- For NPS units: Update 4.02
- Ensure the default passwords are changed prior to deployment

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the Internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs), recognizing VPNs may have vulnerabilities and should be updated to the most current version available. Also recognize VPN is only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- February 4, 2025: Initial Publication

Go to Source
