---
title: "Nedap Librix Ecoreader"
date: 2025-01-08
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 9.3**
- **ATTENTION:** Exploitable remotely/Low attack complexity
- **Vendor:** Nedap Librix
- **Equipment:** Ecoreader
- **Vulnerability:** Missing Authentication for Critical Function

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could result in remote code execution.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following versions of Ecoreader are affected:

- Ecoreader: All versions

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **MISSING AUTHENTICATION FOR CRITICAL FUNCTION CWE-306**

The affected product is missing authentication for critical functions that could allow an unauthenticated attacker to potentially execute malicious code.

CVE-2024-12757 has been assigned to this vulnerability. A CVSS v3 base score of 8.6 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:L/A:L).

A CVSS v4 score has also been calculated for CVE-2024-12757. A base score of 9.3 has been calculated; the CVSS vector string is (AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Commercial Facilities
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Netherlands

### 3.4 RESEARCHER

Prajitesh Singh of Cyble reported this vulnerability to CISA.

## 4\. MITIGATIONS

Nedap Librix did not respond to our attempts to coordinate with them.

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

- January 07, 2025: Initial Publication

Go to Source
