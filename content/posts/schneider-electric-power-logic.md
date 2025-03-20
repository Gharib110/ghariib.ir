---
title: "Schneider Electric Power Logic"
date: 2025-01-29
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v3 8.8**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Schneider Electric
- **Equipment**: Power Logic
- **Vulnerabilities**: Authorization Bypass Through User-Controlled Key, Improper Restriction of Operations within the Bounds of a Memory Buffer

## 2\. RISK EVALUATION

Successful exploitation of these vulnerabilities could allow an attacker to modify data or cause a denial-of-service condition on web interface functionality.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Schneider Electric reports that the following products are affected:

- Schneider Electric Power Logic: v0.62.7 (CVE-2024-10497)
- Schneider Electric Power Logic: v0.62.7 and prior (CVE-2024-10498)

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **AUTHORIZATION BYPASS THROUGH USER-CONTROLLED KEY CWE-639**

An authorization bypass through user-controlled key vulnerability exists that could allow an authorized attacker to modify values outside those defined by their privileges (Elevation of Privileges) when the attacker sends modified HTTPS requests to the device.

CVE-2024-10497 has been assigned to this vulnerability. A CVSS v3 base score of 8.8 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:H).

#### **3.2.2** **IMPROPER RESTRICTION OF OPERATIONS WITHIN THE BOUNDS OF A MEMORY BUFFER CWE-119**

An improper restriction of operations within the bounds of a memory buffer vulnerability exists that could allow an unauthorized attacker to modify configuration values outside of the normal range when the attacker sends specific Modbus write packets to the device, which could result in invalid data or loss of web interface functionality.

CVE-2024-10498 has been assigned to this vulnerability. A CVSS v3 base score of 6.5 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:N/I:L/A:L).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Energy
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** France

### 3.4 RESEARCHER

Schneider Electric CPCERT reported these vulnerabilities to CISA.

## 4\. MITIGATIONS

Schneider Electric has identified the following specific workarounds and mitigations users can apply to reduce risk:

- (CVE-2024-10497) Schneider Electric Power Logic HDPM6000 Version 0.62.7 only: Version v0.62.11 and newer of HDPM6000 includes a fix for these vulnerabilities and is available for download here. A device restart will occur as part of the firmware update process if conducted through the web user interface. If the upgrade is performed using the HDPM6000 Manager software, the device will need to be restarted manually to apply the update.
- (CVE-2024-10497) Schneider Electric Power Logic HDPM6000 Version 0.62.7 only: If users choose not to apply the remediation provided above, they should immediately apply the following mitigations to reduce the risk of exploit: Ensure that the device is not accessible via the HTTPS protocol outside the local network segment by applying appropriate firewalls configuration and controls, and that access to the network segment is protected and controlled.
- (CVE-2024-10498) Schneider Electric Power Logic HDPM6000 Versions 0.62.7 and prior: Version v0.62.11 and newer of HDPM6000 includes a fix for these vulnerabilities and is available for download here. A device restart will occur as part of the firmware update process if conducted through the web user interface. If the upgrade is performed using the HDPM6000 Manager software, the device will need to be restarted manually to apply the update.
- (CVE-2024-10498) Schneider Electric Power Logic HDPM6000 Versions 0.62.7 and prior: If users choose not to apply the remediation provided above, they should immediately apply the following mitigations to reduce the risk of exploit: Ensure that the device is not accessible via the Modbus protocol outside the local network segment by applying appropriate firewalls configuration and controls, and that access to the network segment is protected and controlled.

CISA recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs). Recognize VPNs may have vulnerabilities, should be updated to the most recent version available, and are only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- January 28, 2025: Initial Publication

Go to Source
