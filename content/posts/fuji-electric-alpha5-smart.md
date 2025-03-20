---
title: "Fuji Electric Alpha5 SMART"
date: 2025-01-17
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 8.5**
- **ATTENTION**: Low attack complexity
- **Vendor**: Fuji Electric
- **Equipment**: Alpha5 SMART
- **Vulnerability**: Stack-based Buffer Overflow

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an attacker to execute arbitrary code.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following versions of Fuji Electric Alpha5 SMART, a servo drive system, are affected:

- Alpha5 SMART: Versions 4.5 and prior

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **STACK-BASED BUFFER OVERFLOW CWE-121**

The affected product is vulnerable to a stack-based buffer overflow, which may allow an attacker to execute arbitrary code.

CVE-2024-34579 has been assigned to this vulnerability. A CVSS v3.1 base score of 7.8 has been calculated; the CVSS vector string is (AV:L/AC:L/PR:N/UI:R/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2024-34579. A base score of 8.5 has been calculated; the CVSS vector string is (CVSS4.0/AV:L/AC:L/AT:N/PR:N/UI:P/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Japan

### 3.4 RESEARCHER

An anonymous researcher working with Trend Micro's Zero Day Initiative reported this vulnerability to CISA.

## 4\. MITIGATIONS

Fuji Electric has indicated that the vulnerabilities will not be fixed in Alpha5 SMART. Fuji Electric recommends users upgrade their systems to Alpha7.

For assistance, reach out directly to Fuji Electric's support team.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the Internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs), recognizing VPNs may have vulnerabilities and should be updated to the most current version available. Also recognize VPN is only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time. This vulnerability is not exploitable remotely.

## 5\. UPDATE HISTORY

- January 16, 2025: Initial Publication

Go to Source
