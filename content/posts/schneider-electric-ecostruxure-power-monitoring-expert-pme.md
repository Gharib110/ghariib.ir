---
title: "Schneider Electric EcoStruxure Power Monitoring Expert (PME)"
date: 2025-02-06
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v3 7.1**
- **ATTENTION**: Exploitable remotely
- **Vendor**: Schneider Electric
- **Equipment**: EcoStruxure Power Monitoring Expert (PME)
- **Vulnerability**: Deserialization of Untrusted Data

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an attacker to remotely execute code.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Schneider Electric reports that the following products are affected:

- EcoStruxure Power Monitoring Expert (PME): Versions 2022 and prior

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **DESERIALIZATION OF UNTRUSTED DATA CWE-502**

A deserialization of untrusted data vulnerability exists which could allow code to be remotely executed on the server when unsafely deserialized data is posted to the web server.

CVE-2024-9005 has been assigned to this vulnerability. A CVSS v3 base score of 7.1 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:H/PR:L/UI:R/S:U/C:H/I:H/A:H).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Commercial Facilities, Critical Manufacturing, Energy
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** France

### 3.4 RESEARCHER

Schneider Electric CPCERT reported this vulnerability to CISA.

## 4\. MITIGATIONS

Schneider Electric has identified the following specific workarounds and mitigations users can apply to reduce risk:

- EcoStruxure Power Monitoring Expert 2021 and prior have reached end-of-life support. Users should consider upgrading to the latest version offering of PME to resolve this issue. Please contact Schneider Electric Customer Care Center for more details.
- EcoStruxure Power Monitoring Expert (PME) Version 2022 and prior: There is a hotfix available for EcoStruxure Power Monitoring Expert (PME) that includes a fix for this vulnerability. Contact Schneider Electric's Customer Care Center to download this hotfix.

Schneider Electric strongly recommends the following industry cybersecurity best practices:

- Locate control and safety system networks and remote devices behind firewalls and isolate them from the business network.
- Install physical controls so no unauthorized personnel can access your industrial control and safety systems, components, peripheral equipment, and networks.
- Place all controllers in locked cabinets and never leave them in the "Program" mode.
- Never connect programming software to any network other than the network intended for that device.
- Scan all methods of mobile data exchange with the isolated network such as CDs, USB drives, etc. before use in the terminals or any node connected to these networks.
- Never allow mobile devices that have connected to any other network besides the intended network to connect to the safety or control networks without proper sanitation.
- Minimize network exposure for all control system devices and systems and ensure that they are not accessible from the Internet.
- When remote access is required, use secure methods, such as virtual private networks (VPNs). Recognize that VPNs may have vulnerabilities and should be updated to the most current version available. Also, understand that VPNs are only as secure as the connected devices.

For more information refer to the Schneider Electric recommended cybersecurity best practices document and the associated Schneider Electric security notification SEVD-2024-282-05 in PDF and CSAF.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability. CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

CISA also recommends users take the following measures to protect themselves from social engineering attacks:

- Do not click web links or open attachments in unsolicited email messages.
- Refer to Recognizing and Avoiding Email Scams for more information on avoiding email scams.
- Refer to Avoiding Social Engineering and Phishing Attacks for more information on social engineering attacks.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time. This vulnerability has a high attack complexity.

## 5\. UPDATE HISTORY

- February 06, 2025: Initial Publication

Go to Source
