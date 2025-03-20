---
title: "Schneider Electric Modicon Controllers"
date: 2025-01-02
categories: 
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v3 5.4**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Schneider Electric
- **Equipment**: Modicon Controllers
- **Vulnerability**: Cross-site Scripting

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an attacker to cause a victim's browser to run arbitrary JavaScript when visiting a page containing injected payload.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Schneider Electric reports that the following products are affected:

- Schneider Electric Modicon Controllers M258 / LMC058: All versions
- Schneider Electric Modicon Controllers M262: Versions prior to 5.2.8.26
- Schneider Electric Modicon Controllers M251: Versions prior to 5.2.11.24
- Schneider Electric Modicon Controllers M241: Versions prior to 5.2.11.24

### 3.2 Vulnerability Overview

#### **3.2.1** **IMPROPER NEUTRALIZATION OF INPUT DURING WEB PAGE GENERATION ('CROSS-SITE SCRIPTING') CWE-79**

A Cross-site Scripting  vulnerability exists  where an attacker could cause a victim's browser run arbitrary JavaScript when they visit a page containing the injected payload.

CVE-2024-6528 has been assigned to this vulnerability. A CVSS v3 base score of 5.4 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:L/UI:R/S:C/C:L/I:L/A:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Commercial Facilities, Critical Manufacturing, and Energy
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** France

### 3.4 RESEARCHER

Schneider Electric CPCERT reported this vulnerability to CISA.

## 4\. MITIGATIONS

Schneider Electric has identified the following specific workarounds and mitigations users can apply to reduce risk:

- Schneider Electric Modicon Controllers Version prior to v5.2.11.24: Modicon Controller M241 Firmware version 5.2.11.24 delivered with EcoStruxure Machine Expert v2.2.2 includes a fix for this vulnerability and can be updated through the Schneider Electric Software Update (SESU) application. https://www.se.com/ww/en/product-range/2226-ecostruxure-machine-expert-software/ On the engineering workstation, update to v2.2.2 of EcoStruxure Machine Expert. Update Modicon Controller M241 to the latest Firmware and perform reboot
- Schneider Electric Modicon Controllers Version prior to v5.2.11.24: Modicon Controller M251 Firmware version 5.2.11.24 delivered with EcoStruxure Machine Expert v2.2.2 includes a fix for this vulnerability and can be updated through the Schneider Electric Software Update (SESU) application. https://www.se.com/ww/en/product-range/2226-ecostruxure-machine-expert-software/ On the engineering workstation, update to v2.2.2 of EcoStruxure Machine Expert. Update Modicon Controller M251 to the latest Firmware and perform reboot
- Schneider Electric Modicon Controllers M262 Versions prior to v5.2.8.26: Modicon Controller M262 Firmware version 5.2.8.26 delivered with EcoStruxure Machine Expert v2.2.2 includes a fix for this vulnerability and can be updated through the Schneider Electric Software Update (SESU) application.https://www.se.com/ww/en/product-range/2226-ecostruxure-machine-expert-software/ On the engineering workstation, update to v2.2.2 of EcoStruxure Machine Expert. Update Modicon Controller M262 to the latest Firmware and perform reboot
- Schneider Electric Modicon Controllers Version prior to v5.2.11.24, Schneider Electric Modicon Controllers M258 / LMC058 All versions , Schneider Electric Modicon Controllers M262 Versions prior to v5.2.8.26, Schneider Electric Modicon Controllers Version prior to v5.2.11.24: Users should immediately apply the following mitigations to reduce the risk of exploit: Use controllers and devices only in a protected environment to minimize network exposure and ensure that they are not accessible from public internet or untrusted networks. Ensure usage of user management and password features. User rights are enabled by default and forced to create a strong password at first use. Deactivate the Webserver after use when not needed. Use encrypted communication links. Setup network segmentation and implement a firewall to block all unauthorized access to port 80/HTTP and 443/HTTPS. Use VPN (Virtual Private Networks) tunnels if remote access is required. The "Cybersecurity Guidelines for EcoStruxure Machine Expert, Modicon and PacDrive Controllers and Associated Equipment" provide product specific chapters to ensure you are informed of all updates, including details on affected products and remediation plans, subscribe to Schneider Electric's security notification service here

For more information refer to the Schneider Electric Recommended Cybersecurity Best Practices document and the associated Schneider Electric Security Notification SEVD-2024-191-04 in PDF and CSAF.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs). Recognize VPNs may have vulnerabilities, should be updated to the most recent version available, and are only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

CISA also recommends users take the following measures to protect themselves from social engineering attacks:

- Do not click web links or open attachments in unsolicited email messages.
- Refer to Recognizing and Avoiding Email Scams for more information on avoiding email scams.
- Refer to Avoiding Social Engineering and Phishing Attacks for more information on social engineering attacks.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- December 19, 2024: Initial Publication
