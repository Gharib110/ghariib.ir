---
title: "Schneider Electric Web Designer for Modicon"
date: 2025-02-06
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v3 7.8**
- **ATTENTION**: Low attack complexity
- **Vendor**: Schneider Electric
- **Equipment**: Web Designer for Modicon
- **Vulnerability**: Improper Restriction of XML External Entity Reference

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could result in information disclosure, workstation integrity and potential remote code execution on the compromised computer.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following versions of Web Designer for Modicon are affected:

- Web Designer for BMXNOR0200H: All versions
- Web Designer for BMXNOE0110(H): All versions
- Web Designer for BMENOC0311(C): All versions
- Web Designer for BMENOC0321(C): All versions

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **IMPROPER RESTRICTION OF XML EXTERNAL ENTITY REFERENCE CWE-611**

The affected product is vulnerable to an improper restriction of XML external entity reference vulnerability that could cause information disclosure, impacts to workstation integrity, and potential remote code execution on the compromised computer when a specifically crafted XML file is imported in the Web Designer configuration tool.

CVE-2024-12476 has been assigned to this vulnerability. A CVSS v3.1 base score of 7.8 has been calculated; the CVSS vector string is (AV:L/AC:L/PR:N/UI:R/S:U/C:H/I:H/A:H).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Commercial Facilities, Energy, Food and Agriculture, Government Facilities, Transportation Systems, Water and Wastewater Systems
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** France

### 3.4 RESEARCHER

Jin Huang of ADLab of Venustech reported this vulnerability Schneider Electric.

## 4\. MITIGATIONS

Web Designer tool project file is based on XML language with specific parameters. To ensure the integrity of this file please follow the recommendations below:

- Encrypt project file (XML configuration file) when stored and restrict the access to only trusted users.
- When exchanging files over the network, use secure communication protocols.
- Only open project files received from a trusted source.
- Compute a hash of the project files and regularly check the consistency of this hash to verify the integrity before usage.

To ensure you are informed of all updates, including details on affected products and remediation plans, subscribe to Schneider Electric's security notification service here: https://www.se.com/ww/en/work/support/cybersecurity/security-notifications.jsp

Schneider Electric strongly recommends the following industry cybersecurity best practices.

- Locate control and safety system networks and remote devices behind firewalls and isolate them from the business network.
- Install physical controls so no unauthorized personnel can access your industrial control and safety systems, components, peripheral equipment, and networks.
- Place all controllers in locked cabinets and never leave them in the "Program" mode.
- Never connect programming software to any network other than the network intended for that device.
- Scan all methods of mobile data exchange with the isolated network such as CDs, USB drives, etc. before use in the terminals or any node connected to these networks.
- Never allow mobile devices that have connected to any other network besides the intended network to connect to the safety or control networks without proper sanitation.
- Minimize network exposure for all control system devices and systems and ensure that they are not accessible from the Internet.
- When remote access is required, use secure methods, such as Virtual Private Networks (VPNs). Recognize that VPNs may have their own vulnerabilities and should be updated to the most current version available. Also, understand that VPNs are only as secure as the connected devices.

For more information refer to the Schneider Electric Recommended Cybersecurity Best Practices document.

For more information, see Schneider Electric security notification "SEVD-2025-014-04 Web Server on Modicon M340 and BMXNOE0100/0110, BMXNOR0200H communication modules"

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

CISA also recommends users take the following measures to protect themselves from social engineering attacks:

- Do not click web links or open attachments in unsolicited email messages.
- Refer to Recognizing and Avoiding Email Scams for more information on avoiding email scams.
- Refer to Avoiding Social Engineering and Phishing Attacks for more information on social engineering attacks.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time. This vulnerability is not exploitable remotely.

## 5\. UPDATE HISTORY

- February 4, 2025: Initial Publication

Go to Source
