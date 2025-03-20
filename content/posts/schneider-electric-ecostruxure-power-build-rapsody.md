---
title: "Schneider Electric EcoStruxure Power Build Rapsody"
date: 2025-01-23
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 4.6**
- **ATTENTION**: Low attack complexity
- **Vendor**: Schneider Electric
- **Equipment**: EcoStruxure Power Build Rapsody
- **Vulnerability**: Improper Restriction of Operations within the Bounds of a Memory Buffer

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow local attackers to potentially execute arbitrary code when opening a malicious project file.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Schneider Electric reports the following versions of EcoStruxure Power Build, a configuration program for panel builders, are affected:

- EcoStruxure Power Build Rapsody: Version v2.5.2 NL and prior
- EcoStruxure Power Build Rapsody: Version v2.7.1 FR and prior
- EcoStruxure Power Build Rapsody: Version v2.7.5 ES and prior
- EcoStruxure Power Build Rapsody: Version v2.5.4 INT and prior

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **IMPROPER RESTRICTION OF OPERATIONS WITHIN THE BOUNDS OF A MEMORY BUFFER CWE-119**

An improper restriction of operations within the bounds of a memory buffer vulnerability exists that could allow local attackers to potentially execute arbitrary code when opening a malicious project file.

CVE-2024-11139 has been assigned to this vulnerability. A CVSS v3 base score of 5.3 has been calculated; the CVSS vector string is (CVSS:3.1/AV:L/AC:L/PR:N/UI:R/S:U/C:L/I:L/A:L).

A CVSS v4 score has also been calculated for CVE-2024-11139. A base score of 4.6 has been calculated; the CVSS vector string is (CVSS:4.0/AV:L/AC:L/AT:N/PR:N/UI:A/VC:L/VI:L/VA:L/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Commercial Facilities, Energy, Food and Agriculture, Government Services and Facilities, Transportation Systems, Water and Wastewater Systems
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** France

### 3.4 RESEARCHER

Michael Heinzl reported this vulnerability to CISA.

## 4\. MITIGATIONS

Schneider Electric has the following remediations for users to apply. Please reboot the system after installing the new version:

- EcoStruxure Power Build Rapsody Versions v2.5.2 NL and prior: Version NL v2.7.2 includes a fix for this vulnerability and is available for download.
- EcoStruxure Power Build Rapsody Versions v2.7.1 FR and prior: Version FR v2.7.12 includes a fix for this vulnerability and is available for download.
- EcoStruxure Power Build Rapsody Versions v2.7.5 ES and prior: Version ES v2.7.52 includes a fix for this vulnerability and is available for download.
- EcoStruxure Power Build Rapsody Versions v2.5.4 INT and prior: Schneider Electric is establishing a remediation plan for all future versions of EcoStruxure Power Build Rapsody INT version that will include a fix for this vulnerability. Schneider Electric will update SEVD-2025-014-09 when the remediation is available.

Until installing the new version, users should immediately apply the following mitigations to reduce the risk of exploit:

- Only open projects from trusted sources.
- Ensure use of malware scans before opening any externally created project.
- Encrypt project file when stored and restrict the access to only trusted users.
- When exchanging files over the network, use secure communication protocols.
- Compute a hash of the project files and regularly check the consistency of this hash to verify the integrity before usage.

For more information refer to the Schneider Electric Recommended cybersecurity best practices document and the associated Schneider Electric security notification SEVD-2025-014-09 in PDF and CSAF.

To ensure users are informed of all updates, including details on affected products and remediation plans, subscribe to Schneider Electric's security notification service.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability. CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time. This vulnerability is not exploitable remotely.

## 5\. UPDATE HISTORY

- January 23, 2025: Initial Publication

Go to Source
