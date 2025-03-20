---
title: "Schneider Electric Pro-face GP-Pro EX and Remote HMI"
date: 2025-02-06
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 6.1**
- **ATTENTION**: Exploitable remotely
- **Vendor**: Schneider Electric
- **Equipment**: Pro-face GP-Pro EX and Remote HMI
- **Vulnerability**: Improper Enforcement of Message Integrity During Transmission in a Communication Channel

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow man-in-the-middle attacks, resulting in information disclosure, integrity issues, and operational failures.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following versions of Pro-face GP-Pro EX and Remote HMI are affected:

- Pro-face GP-Pro EX: All versions
- Pro-face Remote HMI: All versions

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **IMPROPER ENFORCEMENT OF MESSAGE INTEGRITY DURING TRANSMISSION IN A COMMUNICATION CHANNEL CWE-924**

The affected products are vulnerable to an improper enforcement of message integrity during transmission in a communication channel vulnerability that could cause partial loss of confidentiality, loss of integrity, and availability of the HMI when attacker performs man-in-the-middle attack by intercepting the communication.

CVE-2024-12399 has been assigned to this vulnerability. A CVSS v3.1 base score of 7.1 has been calculated; the CVSS vector string is (AV:N/AC:H/PR:N/UI:R/S:U/C:L/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2024-12399. A base score of 6.1 has been calculated; the CVSS vector string is (CVSS:4.0/AV:N/AC:H/AT:N/PR:N/UI:P/VC:L/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Energy
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** France

### 3.4 RESEARCHER

Haichuan Xu from the Georgia Institute of Technology reported this vulnerability to Schneider Electric.

## 4\. MITIGATIONS

Schneider Electric is establishing a remediation plan for all future versions of Pro-face GP-Pro EX and Pro-face Remote HMI that will include a fix for this vulnerability. Schneider Electric will provide an update when the remediation is available. Until then, users should immediately apply the following mitigations to reduce the risk of exploit:

For users requiring the use of Pro-face Remote HMI, Schneider Electric recommends using following mitigations:

- Use of Pro-face Connect solution or any other VPN solutions for securing the remote access by encrypting the communication between Pro-face Remote HMI and Pro-face GP-ProEX.
- Always connect the products to only trusted networks and follow the Pro-face Cybersecurity Guidelines.
- Set up a connection password. For more details refer to the GP-Pro EX V4.0 Reference Manual in section "Remote Viewer - Pro-face Remote HMI".

For users not using the Pro-face Remote HMI, Schneider Electric recommends using following mitigations to reduce the risk of exploit:

- Disabling the Pro-face Remote HMI feature (deactivated by default). For more details refer to the GP-Pro EX V4.0 Reference Manual section "Pro-face Remote HMI Settings."

Schneider Electric strongly recommends the following industry cybersecurity best practices.

- Locate control and safety system networks and remote devices behind firewalls and isolate them from the business network.
- Install physical controls so no unauthorized personnel can access your industrial control and safety systems, components, peripheral equipment, and networks.
- Place all controllers in locked cabinets and never leave them in the "Program" mode.
- Never connect programming software to any network other than the network intended for that device.
- Scan all methods of mobile data exchange with the isolated network such as CDs, USB drives, etc. before use in the terminals or any node connected to these networks.
- Never allow mobile devices that have connected to any other network besides the intended network to connect to the safety or control networks without proper sanitation.
- Minimize network exposure for all control system devices and systems and ensure that they are not accessible from the Internet.
- When remote access is required, use secure methods, such as virtual private networks (VPNs). Recognize that VPNs may have vulnerabilities and should be updated to the most current version available. Also, understand that VPNs are only as secure as the connected devices.

For more information refer to the Schneider Electric Recommended Cybersecurity Best Practices document.

For more information, see Schneider Electric security notification "SEVD-2025-014-02 Schneider Electric Security Notification Pro-face GP-Pro EX and Remote HMI"

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

- February 4, 2025: Initial Publication

Go to Source
