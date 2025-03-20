---
title: "Schneider Electric PowerChute Serial Shutdown"
date: 2025-01-12
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
tags: 
  - "vpn"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 6.3**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Schneider Electric
- **Equipment**: PowerChute Serial Shutdown
- **Vulnerability**: Improper Authentication

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could cause a denial of access to the web interface when someone on the local network repeatedly requests the /accessdenied URL.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Schneider Electric reports the following versions of PowerChute Serial Shutdown are affected:

- PowerChute Serial Shutdown: Versions 1.2.0.301 and prior

### 3.2 Vulnerability Overview

#### **3.2.1** **IMPROPER AUTHENTICATION CWE-287**

An improper authentication vulnerability exists that could cause a denial of access to the web interface when someone on the local network repeatedly requests the /accessdenied URL.

CVE-2024-10511 has been assigned to this vulnerability. A CVSS v3.1 base score of 5.3 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:N/UI:N/S:U/C:N/I:N/A:L).

A CVSS v4 score has also been calculated for CVE-2024-10511. A base score of 6.3 has been calculated; the CVSS vector string is (CVSS:4.0/AV:N/AC:L/AT:P/PR:N/UI:N/VC:N/VI:N/VA:L/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** France

### 3.4 RESEARCHER

Schneider Electric reported this vulnerability to CISA.

## 4\. MITIGATIONS

Schneider Electric recommends the following mitigations for the affected product:

- PowerChute Serial Shutdown: Versions v1.2.0.301 and prior: Update to PowerChute Serial Shutdown: Version 1.3

For users to be informed of all updates, including details on affected products and remediation plans, subscribe to Schneider Electric's security notification service here:  
https://www.se.com/ww/en/work/support/cybersecurity/notification-contact.jsp

Schneider Electric strongly recommend the following industry cybersecurity best practices:

- Locate control and safety system networks and remote devices behind firewalls and isolate them from the business network.
- Install physical controls so no unauthorized personnel can access your industrial control and safety systems, components, peripheral equipment, and networks.
- Place all controllers in locked cabinets and never leave them in the "Program" mode.
- Never connect programming software to any network other than the network intended for that device.
- Scan all methods of mobile data exchange with the isolated network such as CDs, USB drives, etc. before use in the terminals or any node connected to these networks.
- Never allow mobile devices that have connected to any other network besides the intended network to connect to the safety or control networks without proper sanitation.
- Minimize network exposure for all control system devices and systems and ensure that they are not accessible from the Internet.
- When remote access is required, use secure methods, such as Virtual Private Networks (VPNs). Recognize that VPNs may have vulnerabilities and should be updated to the most current version available. Also, understand that VPNs are only as secure as the connected devices.

For more information refer to the Schneider Electric Recommended Cybersecurity Best Practices document and the associated Schneider Electric Security Notification SEVD-2024-345-01 in PDF and CSAF.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

CISA also recommends users take the following measures to protect themselves from social engineering attacks:

- Do not click web links or open attachments in unsolicited email messages.
- Refer to Recognizing and Avoiding Email Scams for more information on avoiding email scams.
- Refer to Avoiding Social Engineering and Phishing Attacks for more information on social engineering attacks.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- January 10, 2025: Initial Publication

Go to Source
