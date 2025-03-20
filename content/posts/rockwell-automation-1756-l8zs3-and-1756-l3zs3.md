---
title: "Rockwell Automation 1756-L8zS3 and 1756-L3zS3"
date: 2025-02-06
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 7.1**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Rockwell Automation
- **Equipment**: 1756-L8zS3, 1756-L3zS3
- **Vulnerability**: Improper Handling of Exceptional Conditions

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow a remote, non-privileged user to send malicious requests resulting in a major nonrecoverable fault causing a denial-of-service condition.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following Rockwell Automation products are affected:

- 1756-L8zS3: Versions prior to V33.017, V34.014, V35.013, V36.011
- 1756-L3zS3: Versions prior to V33.017, V34.014, V35.013, V36.011

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **Improper Handling of Exceptional Conditions CWE-755**

A denial-of-service vulnerability exists in the affected products. The vulnerability could allow a remote, non-privileged user to send malicious requests resulting in a major nonrecoverable fault causing a denial-of-service.

CVE-2025-24478 has been assigned to this vulnerability. A CVSS v3.1 base score of 6.5 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:L/UI:N/S:U/C:N/I:N/A:H).

A CVSS v4 score has also been calculated for CVE-2025-24478. A base score of 7.1 has been calculated; the CVSS vector string is (AV:N/AC:L/AT:N/PR:L/UI:N/VC:N/VI:N/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** United States

### 3.4 RESEARCHER

Rockwell Automation reported this vulnerability to CISA.

## 4\. MITIGATIONS

Rockwell Automation recommends users of the affected software to apply the risk mitigations, if possible.

- Update to V33.017, V34.014, V35.013, V36.011, or the latest version.
- Restrict Access to the task object via CIP Security and Hard Run.
- For information on how to mitigate security risks on industrial automation control systems, Rockwell Automation encourages users to implement our suggested security best practices to minimize the risk of the vulnerability.

Stakeholder-Specific Vulnerability Categorization can be used to generate more environment-specific prioritization.

For more information about this issue, please see the advisory on the Rockwell Automation security page.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

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

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- February 4, 2025: Initial Publication

Go to Source
