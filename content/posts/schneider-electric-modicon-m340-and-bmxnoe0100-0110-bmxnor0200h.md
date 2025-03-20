---
title: "Schneider Electric Modicon M340 and BMXNOE0100/0110, BMXNOR0200H"
date: 2025-02-06
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v3 8.6**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Schneider Electric
- **Equipment**: Modicon M340 and BMXNOE0100/0110, BMXNOR0200H
- **Vulnerability**: Exposure of Sensitive Information to an Unauthorized Actor

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could cause information disclosure of a restricted web page, modification of a web page, and a denial of service when specific web pages are modified and restricted functions invoked.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following Schneider Electric products, Modicon M340 and BMXNOE0100/0110, BMXNOR0200H, are affected:

- Modicon M340 processors (part numbers BMXP34\*): All versions
- BMXNOE0100: All versions
- BMXNOE0110: All versions
- BMXNOR0200H: Versions prior to SV1.70IR26

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **EXPOSURE OF SENSITIVE INFORMATION TO AN UNAUTHORIZED ACTOR CWE-200**

The affected products are vulnerable to an exposure of sensitive information to an unauthorized actor vulnerability, which could cause information disclosure of restricted web page, modification of web page, and denial of service when specific web pages are modified and restricted functions invoked.

CVE-2024-12142 has been assigned to this vulnerability. A CVSS v3.1 base score of 8.6 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:N/UI:N/S:U/C:L/I:L/A:H).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Commercial Facilities, Critical Manufacturing, Energy
- **COUNTRIES/AREAS DEPLOYED:** France
- **COMPANY HEADQUARTERS LOCATION:** Worldwide

### 3.4 RESEARCHER

Schneider Electric reported this vulnerability to CISA.

## 4\. MITIGATIONS

Schneider Electric has identified the following specific workarounds and mitigations users can apply to reduce risk:

BMXNOR0200H: Version SV1.70IR26 of BMXNOR0200H includes a fix for this vulnerability and is available for download.

Users should use appropriate patching methodologies when applying these patches to their systems. Schneider Electric strongly recommends the use of back-ups and evaluating the impact of these patches in a testing and development environment, or on an offline infrastructure. Contact Schneider Electric's Customer Care Center for assistance removing a patch.

Schneider Electric is establishing a remediation plan for all future versions of Modicon M340 processors BMXP34\*, BMXNOE0100 and BMXNOE0110 that will include a fix for this vulnerability. They will provide an update when the remediation is available. Until then, users should immediately apply the following mitigations to reduce the risk of exploit:

- Set up network segmentation and implement a firewall to block all unauthorized access to FTP Port 21/TCP on the devices.
- Disable FTP service via EcoStruxureTM Control Expert. This is disabled by default when a new application is created.
- Disable Web server service via EcoStruxureTM Control Expert. This is disabled by default when a new application is created.
- Configure the Access Control List following the recommendation on the "Modicon Controllers System Cybersecurity"

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

For more information, see Schneider Electric security notification "SEVD-2025-014-05 Web Server on Modicon M340 and BMXNOE0100/0110, BMXNOR0200H communication modules"

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- February 4, 2025: Initial Publication

Go to Source
