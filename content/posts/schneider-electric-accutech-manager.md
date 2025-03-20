---
title: "Schneider Electric Accutech Manager"
date: 2025-01-02
categories: 
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v3 7.5**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Schneider Electric
- **Equipment**: Accutech Manager
- **Vulnerability**: Classic Buffer Overflow
    
    ## 2\. RISK EVALUATION
    

Successful exploitation could allow an attacker to cause a crash of the Accutech Manager when receiving a specially crafted request over port 2536/TCP.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Schneider Electric reports that the following products are affected:

- Schneider Electric Accutech Manager: Versions 2.08.01 and prior

### 3.2 Vulnerability Overview

#### **3.2.1** **BUFFER COPY WITHOUT CHECKING SIZE OF INPUT ('CLASSIC BUFFER OVERFLOW') CWE-120**

A Classic Buffer Overflow vulnerability exists that could cause a crash of the Accutech Manager when receiving a specially crafted request over port 2536/TCP.

CVE-2024-6918 has been assigned to this vulnerability. A CVSS v3 base score of 7.5 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:N/I:N/A:H).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Energy, Water and Wastewater, Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** France

### 3.4 RESEARCHER

Schneider Electric reported this vulnerability to CISA.

## 4\. MITIGATIONS

Schneider Electric has identified the following specific workarounds and mitigations users can apply to reduce risk:

- Update Schneider Electric Accutech Manager to version 2.10.0.
- Instructions are provided with the software installation package on how to verify software revision.

For more information refer to the Schneider Electric Recommended Cybersecurity Best Practices document and the associated Schneider Electric Security Notification SEVD-2024-226-01 in PDF and CSAF.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs). Recognize VPNs may have vulnerabilities, should be updated to the most recent version available, and are only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- December 19, 2024: Initial Publication
