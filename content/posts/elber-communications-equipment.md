---
title: "Elber Communications Equipment"
date: 2025-02-06
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 9.3**
- **ATTENTION**: Exploitable remotely/low attack complexity/public exploits are available
- **Vendor**: Elber
- **Equipment**: Communications Equipment
- **Vulnerabilities**: Authentication Bypass Using an Alternate Path or Channel, Hidden Functionality

## 2\. RISK EVALUATION

Successful exploitation of these vulnerabilities could allow an attacker unauthorized administrative access to the affected device.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following versions of Elber Communications Equipment are affected:

- Signum DVB-S/S2 IRD: Versions 1.999 and prior
- Cleber/3 Broadcast Multi-Purpose Platform: Version 1.0
- Reble610 M/ODU XPIC IP-ASI-SDH: Version 0.01
- ESE DVB-S/S2 Satellite Receiver: Versions 1.5.179 and prior
- Wayber Analog/Digital Audio STL: Version 4

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **Authentication Bypass Using an Alternate Path or Channel CWE-288**

Multiple Elber products are affected by an authentication bypass vulnerability which allows unauthorized access to the password management functionality. Attackers can exploit this issue by manipulating the endpoint to overwrite any user's password within the system. This grants them unauthorized administrative access to protected areas of the application, compromising the device's system security.

CVE-2025-0674 has been assigned to this vulnerability. A CVSS v3.1 base score of 9.8 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2025-0674. A base score of 9.3 has been calculated; the CVSS vector string is (CVSS4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

#### **3.2.2** **Hidden Functionality CWE-912**

Multiple Elber products suffer from an unauthenticated device configuration and client-side hidden functionality disclosure.

CVE-2025-0675 has been assigned to this vulnerability. A CVSS v3.1 base score of 7.5 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N).

A CVSS v4 score has also been calculated for CVE-2025-0675. A base score of 8.7 has been calculated; the CVSS vector string is (CVSS4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:N/VA:N/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Communications
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Italy

### 3.4 RESEARCHER

Gjoko Krstic of Zero Science Lab reported these vulnerabilities to CISA.

## 4\. MITIGATIONS

Elber does not plan to mitigate these vulnerabilities because this equipment is either end of life or almost end of life. Users of affected versions of Elber Signum DVB-S/S2 IRD, Cleber/3 Broadcast Multi-Purpose Platform, Reble610 M/ODU XPIC IP-ASI-SDH, ESE DVB-S/S2 Satellite Receiver, and Wayber Analog/Digital Audio STL are invited to contact Elber customer support for additional information.

CISA recommends users take defensive measures to minimize the risk of exploitation of this these vulnerabilities, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs), recognizing VPNs may have vulnerabilities and should be updated to the most current version available. Also recognize VPN is only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

CISA also recommends users take the following measures to protect themselves from social engineering attacks:

- Do not click web links or open attachments in unsolicited email messages.
- Refer to Recognizing and Avoiding Email Scams for more information on avoiding email scams.
- Refer to Avoiding Social Engineering and Phishing Attacks for more information on social engineering attacks.

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- February 4, 2025: Initial Publication

Go to Source
