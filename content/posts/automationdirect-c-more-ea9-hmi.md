---
title: "AutomationDirect C-more EA9 HMI"
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
- **Vendor**: AutomationDirect
- **Equipment**: C-more EA9 HMI
- **Vulnerability**: Buffer Copy without Checking Size of Input ('Classic Buffer Overflow')

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an attacker to cause a denial-of-service condition or achieve remote code execution on the affected device.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following Automation Direct products are affected:

- C-more EA9 HMI EA9-T6CL: v6.79 and prior
- C-more EA9 HMI EA9-T7CL-R: v6.79 and prior
- C-more EA9 HMI EA9-T7CL: v6.79 and prior
- C-more EA9 HMI EA9-T8CL: v6.79 and prior
- C-more EA9 HMI EA9-T10CL: v6.79 and prior
- C-more EA9 HMI EA9-T10WCL: v6.79 and prior
- C-more EA9 HMI EA9-T12CL: v6.79 and prior
- C-more EA9 HMI EA9-T15CL-R: v6.79 and prior
- C-more EA9 HMI EA9-T15CL: v6.79 and prior
- C-more EA9 HMI EA9-RHMI: v6.79 and prior

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **Buffer Copy without Checking Size of Input ('Classic Buffer Overflow') CWE-120**

AutomationDirect C-more EA9 HMI contains a function with bounds checks that can be skipped, which could result in an attacker abusing the function to cause a denial-of-service condition or achieving remote code execution on the affected device.

CVE-2025-0960 has been assigned to this vulnerability. A CVSS v3.1 base score of 9.8 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2025-0960. A base score of 9.3 has been calculated; the CVSS vector string is (AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** United States

### 3.4 RESEARCHER

Sharon Brizinov of Claroty Team82 reported this vulnerability to CISA.

## 4\. MITIGATIONS

AutomationDirect recommends that users update C-MORE EA9 HMI software and firmware to V6.80.

If an immediate update is not feasible, AutomationDirect recommends considering the following interim steps until the programming software can be updated:

- Isolate the HMI Workstation: Disconnect the HMI from external networks (e.g., internet or corporate LAN) to limit exposure to external threats.
- Use dedicated, secure internal networks or air-gapped systems for communication with programmable devices.
- Control Access: Restrict physical and logical access to the HMI to authorized personnel only.
- Implement Whitelisting: Use application whitelisting to allow only pre-approved and trusted software to execute on the HMI. Block untrusted or unauthorized applications.
- Apply Endpoint Security Measures: Use antivirus or endpoint detection and response (EDR) tools to monitor for and mitigate threats. Ensure that host-based firewalls are properly configured to block unauthorized access.
- Monitor and Log Activity: Enable logging and monitoring of system activities to detect potential anomalies or unauthorized actions. Regularly review logs for suspicious activity.
- Use Secure Backup and Recovery: Regularly back up the workstation and its configurations to a secure location. Test recovery procedures to ensure minimal downtime in the event of an incident.
- Conduct Regular Risk Assessments: Continuously assess the risks posed by the outdated software and adjust mitigation measures as necessary.

For more information, please see the AutomationDirect security advisory.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs), recognizing VPNs may have vulnerabilities and should be updated to the most current version available. Also recognize VPN is only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- February 4, 2025: Initial Publication

Go to Source
