---
title: "New Rock Technologies Cloud Connected Devices"
date: 2025-02-01
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 9.3**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: New Rock Technologies
- **Equipment**: Cloud Connected Devices
- **Vulnerabilities**: Improper Neutralization of Special Elements used in an OS Command ('OS Command Injection'), Improper Neutralization of Wildcards or Matching Symbols

## 2\. RISK EVALUATION

Successful exploitation of these vulnerabilities could allow an attacker full control of the device.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following versions of New Rock Technologies Cloud Connected Devices are affected:

- OM500 IP-PBX: All versions
- MX8G VoIP Gateway: All versions
- NRP1302/P Desktop IP Phone: All versions

### 3.2 Vulnerability Overview

#### **3.2.1** **Improper Neutralization of Special Elements used in an OS Command ('OS Command Injection') CWE-78**

Affected products contain a vulnerability in the device cloud rpc command handling process that could allow remote attackers to take control over arbitrary devices connected to the cloud.

CVE-2025-0680 has been assigned to this vulnerability. A CVSS v3.1 base score of 9.8 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2025-0680. A base score of 9.3 has been calculated; the CVSS vector string is (AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

#### **3.2.2** **Improper Neutralization of Wildcards or Matching Symbols CWE-155**

The Cloud MQTT service of the affected products supports wildcard topic subscription which could allow an attacker to obtain sensitive information from tapping the service communications.

CVE-2025-0681 has been assigned to this vulnerability. A CVSS v3.1 base score of 6.2 has been calculated; the CVSS vector string is (AV:L/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N).

A CVSS v4 score has also been calculated for CVE-2025-0681. A base score of 6.9 has been calculated; the CVSS vector string is (AV:L/AC:L/AT:N/PR:N/UI:N/VC:H/VI:N/VA:N/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Communications, Healthcare and Public Health
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** China

### 3.4 RESEARCHER

Tomer Goldschmidt of Claroty Team82 reported these vulnerabilities to CISA.

## 4\. MITIGATIONS

New Rock Technologies has not responded to requests to work with CISA to mitigate these vulnerabilities. Users of affected versions of New Rock Technologies Cloud Connected Devices are invited to contact New Rock Technologies customer support for additional information.

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

- January 30, 2025: Initial Publication

Go to Source
