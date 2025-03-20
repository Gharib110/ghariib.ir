---
title: "Schneider Electric Modicon M580 PLCs, BMENOR2200H and EVLink Pro AC"
date: 2025-02-06
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 8.7**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Schneider Electric
- **Equipment**: Modicon M580 PLCs, BMENOR2200H and EVLink Pro AC
- **Vulnerability**: Incorrect Calculation of Buffer Size

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could cause a denial-of-service of the product when an unauthenticated user sends a crafted HTTPS packet to the webserver.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following versions of Modicon M580 PLCs, BMENOR2200H and EVLink Pro AC are affected:

- Modicon M580 CPU (part numbers BMEP\* and BMEH\*, excluding M580 CPU Safety): Versions prior to SV4.30
- Modicon M580 CPU Safety (part numbers BMEP58-S and BMEH58-S): Versions prior to SV4.21
- BMENOR2200H: All versions
- EVLink Pro AC: Versions prior to v1.3.10

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **INCORRECT CALCULATION OF BUFFER SIZE CWE-131**

The affected product is vulnerable to an incorrect calculation of buffer size vulnerability which could cause a denial-of-service of the product when an unauthenticated user is sending a crafted HTTPS packet to the webserver.

CVE-2024-11425 has been assigned to this vulnerability. A CVSS v3.1 base score of 7.5 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:N/UI:N/S:U/C:N/I:N/A:H).

A CVSS v4 score has also been calculated for CVE-2024-11425. A base score of 8.7 has been calculated; the CVSS vector string is (CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:N/VI:N/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Commercial Facilities, Critical Manufacturing, Energy
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** France

### 3.4 RESEARCHER

Schneider Electric reported this vulnerability to CISA.

## 4\. MITIGATIONS

Schneider Electric has identified the following remediations users can apply to reduce risk:

- Modicon M580 CPU (partnumbers BMEP\* and BMEH\*,excluding M580 CPU Safety): Version SV4.30 of Modicon M580 firmware includes a fix for this vulnerability and is available for download.
- Modicon M580 CPU Safety part numbers BMEP58-S and MEH58-S): Version SV4.21 of Modicon M580 firmware includes a fix for this vulnerability and is available for download.
- EVLink Pro AC: Version V1.3.10 of EVLink Pro AC firmware includes a fix for this vulnerability and is available here.

Users should use appropriate patching methodologies when applying these patches to their systems. Schneider Electric strongly recommends making use of back-ups and evaluating the impact of these patches in a testing and development environment or on an offline infrastructure. Contact Schneider Electric's Customer Care Center if assistance is needed for removing a patch.

If users choose not to apply the remediation provided above, they should immediately apply the following mitigations to reduce the risk of exploit:

- Modicon M580 CPU (partnumbers BMEP\* and BMEH\*,excluding M580 CPU Safety): Set up network segmentation and implement a firewall to block all unauthorized access to Port 443/TCP. Configure the access control list following the recommendations of the user manuals: "Modicon M580, Hardware, Reference Manual"
- Modicon M580 CPU Safety part numbers BMEP58-S and MEH58-S): Set up network segmentation and implement a firewall to block all unauthorized access to Port 443/TCP. Configure the access control list following the recommendations of the user manuals: "Modicon M580, Hardware, Reference Manual"
- BMENOR2200H: Schneider Electric is establishing a remediation plan for BMENOR2200H that will include a fix for CVE-2024-11425. They will update SEVD-2025-014-01 when the remediation is available. Until then, users should immediately set up network segmentation and implement a firewall to block all unauthorized access to Port 443/TCP.
- EVLink Pro AC: Follow the EVlink Pro AC cybersecurity guide

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

For more information, see Schneider Electric security notification "SEVD-2025-014-01 Modicon M580 PLCs, BMENOR2200H and EVLink Pro AC"

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- February 4, 2025: Initial Publication

Go to Source
