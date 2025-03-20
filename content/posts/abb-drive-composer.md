---
title: "ABB Drive Composer"
date: 2025-02-06
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 9.3**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: ABB
- **Equipment**: Drive Composer
- **Vulnerability**: Improper Limitation of a Pathname to a Restricted Directory ('Path Traversal')

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow attackers unauthorized access to the file system on the host machine. An attacker can exploit this flaw to run malicious code, which could lead to the compromise of the affected system.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

ABB reports that the following Drive Composer products are affected:

- Drive Composer entry: Version 2.9.0.1 and prior
- Drive Composer pro: Version 2.9.0.1 and prior

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **IMPROPER LIMITATION OF A PATHNAME TO A RESTRICTED DIRECTORY ('PATH TRAVERSAL') CWE-22**

A vulnerability in drive composer can allow attackers unauthorized access to the file system on the host machine. An attacker can exploit this flaw to run malicious code, which could lead to the compromise of the affected system.

CVE-2024-48510 has been assigned to this vulnerability. A CVSS v3 base score of 9.8 has been calculated; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2024-48510. A base score of 9.3 has been calculated; the CVSS vector string is (CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Switzerland

### 3.4 RESEARCHER

ABB reported this vulnerability to CISA.

## 4\. MITIGATIONS

ABB has corrected this vulnerability in Drive Composer Version 2.9.1. Drive Composer Version 2.9.1 (both entry and pro) is downloadable from the product page. ABB recommends users apply the update at their earliest convenience.

For more information, please refer to the ABB Cybersecurity Advisory.

ABB recommends the following general security practices for any installation of software-related ABB products:

- Isolate special purpose networks (e.g. for automation systems) and remote devices behind firewalls and separate them from any general-purpose network (e.g. office or home networks).
- Install physical controls so no unauthorized personnel can access your devices, components, peripheral equipment, and networks.
- Never connect programming software or computers containing programing software to any network  
    other than the network for the devices that it is intended for.
- Scan all data imported into your environment before use to detect potential malware infections.
- Minimize network exposure for all applications and endpoints to ensure that they are not accessible from the Internet unless they are designed for such exposure and the intended use requires such.
- Ensure all nodes are always up to date in terms of installed software, operating system, and firmware patches as well as anti-virus and firewall.
- When remote access is required, use secure methods, such as virtual private networks (VPNs). Recognize that VPNs may have vulnerabilities and should be updated to the most current version available. Also, understand that VPNs are only as secure as the connected devices.

More information on recommended practices can be found in the following documents:  
3AXD10000492137 Technical Guide - Cybersecurity for ABB Drives

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability. CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- February 6, 2025: Initial Publication

Go to Source
