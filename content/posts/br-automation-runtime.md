---
title: "<div>B&R Automation Runtime</div>"
date: 2025-01-29
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v3 7.5**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: B&R
- **Equipment**: Automation Runtime
- **Vulnerability**: Use of a Broken or Risky Cryptographic Algorithm

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an attacker to masquerade as legitimate services on impacted devices.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

B&R reports that the following products are affected:

- B&R Automation Runtime: versions prior to 6.1
- B&R mapp View: versions prior to 6.1

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **USE OF A BROKEN OR RISKY CRYPTOGRAPHIC ALGORITHM CWE-327**

A "Use of a Broken or Risky Cryptographic Algorithm" vulnerability in the SSL/TLS component used in B&R Automation Runtime versions <6.1 and B&R mapp View versions <6.1 may be abused by unauthenticated network-based attackers to masquerade as legitimate services on impacted devices.

CVE-2024-8603 has been assigned to this vulnerability. A CVSS v3 base score of 7.5 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:N/I:H/A:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Austria

### 3.4 RESEARCHER

ABB PSIRT reported this vulnerability to CISA.

## 4\. MITIGATIONS

B&R has identified the following specific workarounds and mitigations users can apply to reduce risk:

- All affected products: The problem is corrected in the following product versions: B&R Automation Runtime version 6.1 and B&R mapp View 6.1. B&R recommends that customers apply the update at their earliest convenience if B&R Automation Runtime or B&R mapp View is used to generate self-signed certificates on production machines.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs). Recognize VPNs may have vulnerabilities, should be updated to the most recent version available, and are only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- January 28, 2025: Initial Publication

Go to Source
