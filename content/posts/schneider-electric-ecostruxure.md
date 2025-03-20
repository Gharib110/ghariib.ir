---
title: "Schneider Electric EcoStruxure"
date: 2025-02-06
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 8.5**
- **ATTENTION**: Low attack complexity
- **Vendor**: Schneider Electric
- **Equipment**: EcoStruxure
- **Vulnerability**: Uncontrolled Search Path Element

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability allows for local privilege escalation, which could lead to the execution of a malicious Dynamic-Link Library (DLL).

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following Schneider Electric EcoStruxure products and versions, which incorporate Revenera FlexNet Publisher, are affected:

- EcoStruxure Control Expert: Versions prior to V16.1
- EcoStruxure Process Expert: All versions
- EcoStruxure OPC UA Server Expert: All versions
- EcoStruxure Control Expert Asset Link: Versions prior to V4.0 SP1
- EcoStruxure Machine SCADA Expert Asset Link: All versions
- EcoStruxure Architecture Builder: Versions prior to V7.0.18
- EcoStruxure Operator Terminal Expert: All versions
- Vijeo Designer: Version prior to V6.3SP1 HF1
- EcoStruxure Machine Expert including EcoStruxure Machine Expert Safety: All versions
- EcoStruxure Machine Expert Twin: All versions
- Zelio Soft 2: All versions

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **Uncontrolled Search Path Element CWE-427**

A misconfiguration in lmadmin.exe of FlexNet Publisher versions prior to 2024 R1 (11.19.6.0) allows the OpenSSL configuration file to load from a non-existent directory. An unauthorized, locally authenticated user with low privileges can potentially create the directory and load a specially crafted openssl.conf file leading to the execution of a malicious DLL (Dynamic-Link Library) with elevated privileges.

CVE-2024-2658 has been assigned to this vulnerability. A CVSS v3.1 base score of 7.8 has been calculated; the CVSS vector string is (AV:L/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2024-2658. A base score of 8.5 has been calculated; the CVSS vector string is (AV:L/AC:L/AT:N/PR:L/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Commercial Facilities, Energy, Food and Agriculture, Government Services and Facilities, Transportation Systems, Water and Wastewater Systems
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** France

### 3.4 RESEARCHER

Xavier DANEST of Trend Micro Zero Day Initiative reported this vulnerability to Revenera PSIRT.

## 4\. MITIGATIONS

Schneider Electric recommends that users of the following products follow these actions:

- EcoStruxure Control Expert: Versions prior to V16.1 - Version V16.1 of EcoStruxure Control Expert includes a fix for this vulnerability and is available for download here. Reboot the computer after installation is completed.
- EcoStruxure Architecture Builder: Versions prior to V7.0.18 - Version V7.0.18 of EcoStruxure Architecture Builder includes a fix for this vulnerability and is available for download here.
- EcoStruxure Control Expert Asset Link: Versions prior to V4.0 SP1 - Version V4.0SP1 of EcoStruxure Control Expert Asset Link includes a fix for this vulnerability and is available for download here.
- Vijeo Designer: Version prior to V6.3SP1 HF1 - Version V6.3SP1 HF1 of Vijeo Designer includes a fix for this vulnerability. Please contact your Schneider Electric Customer Support to get Vijeo Designer version V6.3SP1 HF1 software.

Users should follow appropriate patching methodologies when applying these patches to their systems. We strongly recommend the use of back-ups and evaluating the impact of these patches in a Test and Development environment or an offline infrastructure. Contact Schneider Electric's Customer Care Center if you need assistance removing a patch.

If users choose not to apply the remediation provided above, they should immediately apply the following mitigations in order to reduce the risk of exploit:

Schneider Electric is establishing a remediation plan for all future versions of the following that will include a fix for this vulnerability:

- EcoStruxure Process Expert
- EcoStruxure OPC UA Server Expert
- EcoStruxure Machine SCADA Expert - Asset Link
- EcoStruxure Operator Terminal Expert
- EcoStruxure Machine Expert including
- EcoStruxure Machine Expert Safety
- EcoStruxure Machine Expert Twin
- Zelio Soft 2

We will update this document when the remediation is available. Until then, users should immediately apply the following mitigations to reduce the risk of exploit:

- Limit authenticated user access to the workstation and implement existing User Account Control practices.
- Follow workstation, network and site-hardening guidelines in the Recommended Cybersecurity Best Practices guide available for download here.

To ensure you are informed of all updates, including details on affected products and remediation plans, subscribe to Schneider Electric's security notification service here.

General Security Recommendations

Schneider Electric strongly recommends the following industry cybersecurity best practices:

- Locate control and safety system networks and remote devices behind firewalls and isolate them from the business network.
- Install physical controls so no unauthorized personnel can access your industrial control and safety systems, components, peripheral equipment, and networks.
- Place all controllers in locked cabinets and never leave them in the "Program" mode.
- Never connect programming software to any network other than the network intended for that device.
- Scan all methods of mobile data exchange with the isolated network such as CDs, USB drives, etc. before use in the terminals or any node connected to these networks.
- Never allow mobile devices that have connected to any other network besides the intended network to connect to the safety or control networks without proper sanitation.
- Minimize network exposure for all control system devices and systems and ensure that they are not accessible from the Internet.
- When remote access is required, use secure methods, such as Virtual Private Networks (VPNs). Recognize that VPNs may have vulnerabilities and should be updated to the most current version available. Also, understand that VPNs are only as secure as the connected devices.

For more information refer to the Schneider Electric Recommended Cybersecurity Best Practices document.

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

- February 6, 2025: Initial Publication

Go to Source
