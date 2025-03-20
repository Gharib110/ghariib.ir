---
title: "Delta Electronics DTM Soft"
date: 2025-01-02
categories: 
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 8.5**
- **ATTENTION**: Low attack complexity
- **Vendor**: Delta Electronics
- **Equipment**: DTM Soft
- **Vulnerability**: Deserialization of Untrusted Data

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an attacker to execute arbitrary code.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following Delta Electronics products are affected:

- DTM Soft: Versions 1.30 and prior

### 3.2 Vulnerability Overview

#### **3.2.1** **DESERIALIZATION OF UNTRUSTED DATA CWE-502**

The affected product deserializes objects, which could allow an attacker to execute arbitrary code.

CVE-2024-12677 has been assigned to this vulnerability. A CVSS v3.1 base score of 7.8 has been calculated; the CVSS vector string is (AV:L/AC:L/PR:N/UI:R/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2024-12677. A base score of 8.5 has been calculated; the CVSS vector string is (CVSS4.0/AV:L/AC:L/AT:N/PR:N/UI:P/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Taiwan

### 3.4 RESEARCHER

kimiya working with Trend Micro Zero Day Initiative reported this vulnerability to CISA.

## 4\. MITIGATIONS

Delta Electronics recommends users update DTM Soft to version 1.60.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs), recognizing VPNs may have vulnerabilities and should be updated to the most current version available. Also recognize VPN is only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time. This vulnerability is not exploitable remotely.

## 5\. UPDATE HISTORY

- December 19, 2024: Initial Publication
