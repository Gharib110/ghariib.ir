---
title: "Siemens SIMATIC S7-1200 CPUs"
date: 2025-01-22
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

As of January 10, 2023, CISA will no longer be updating ICS security advisories for Siemens product vulnerabilities beyond the initial advisory. For the most up-to-date information on vulnerabilities in this advisory, please see Siemens' ProductCERT Security Advisories (CERT Services | Services | Siemens Global).

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 7.2**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Siemens
- **Equipment**: SIMATIC S7-1200 CPUs
- **Vulnerability**: Cross-Site Request Forgery

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an unauthenticated attacker to change the CPU mode by tricking a legitimate and authenticated user with sufficient permissions on the target CPU to click on a malicious link.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Siemens reports that the following products are affected:

- SIMATIC S7-1200 CPU 1211C AC/DC/Rly (6ES7211-1BE40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1214C DC/DC/DC (6ES7214-1AG40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1214C DC/DC/Rly (6ES7214-1HG40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1214FC DC/DC/DC (6ES7214-1AF40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1214FC DC/DC/Rly (6ES7214-1HF40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1215C AC/DC/Rly (6ES7215-1BG40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1215C DC/DC/DC (6ES7215-1AG40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1215C DC/DC/Rly (6ES7215-1HG40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1215FC DC/DC/DC (6ES7215-1AF40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1215FC DC/DC/Rly (6ES7215-1HF40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1217C DC/DC/DC (6ES7217-1AG40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1211C DC/DC/DC (6ES7211-1AE40-0XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1212 AC/DC/RLY (6AG1212-1BE40-2XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1212 AC/DC/RLY (6AG1212-1BE40-4XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1212 DC/DC/RLY (6AG1212-1HE40-2XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1212 DC/DC/RLY (6AG1212-1HE40-4XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1212C DC/DC/DC (6AG1212-1AE40-2XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1212C DC/DC/DC (6AG1212-1AE40-4XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1212C DC/DC/DC RAIL (6AG2212-1AE40-1XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1214 AC/DC/RLY (6AG1214-1BG40-2XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1214 AC/DC/RLY (6AG1214-1BG40-4XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1214 AC/DC/RLY (6AG1214-1BG40-5XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1211C DC/DC/Rly (6ES7211-1HE40-0XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1214 DC/DC/DC (6AG1214-1AG40-2XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1214 DC/DC/DC (6AG1214-1AG40-4XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1214 DC/DC/DC (6AG1214-1AG40-5XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1214 DC/DC/RLY (6AG1214-1HG40-2XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1214 DC/DC/RLY (6AG1214-1HG40-4XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1214 DC/DC/RLY (6AG1214-1HG40-5XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1214C DC/DC/DC RAIL (6AG2214-1AG40-1XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1214FC DC/DC/DC (6AG1214-1AF40-5XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1214FC DC/DC/RLY (6AG1214-1HF40-5XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1215 AC/DC/RLY (6AG1215-1BG40-2XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1212C AC/DC/Rly (6ES7212-1BE40-0XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1215 AC/DC/RLY (6AG1215-1BG40-4XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1215 AC/DC/RLY (6AG1215-1BG40-5XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1215 DC/DC/DC (6AG1215-1AG40-2XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1215 DC/DC/DC (6AG1215-1AG40-4XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1215 DC/DC/RLY (6AG1215-1HG40-2XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1215 DC/DC/RLY (6AG1215-1HG40-4XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1215 DC/DC/RLY (6AG1215-1HG40-5XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1215C DC/DC/DC (6AG1215-1AG40-5XB0): Versions prior to V4.7
- SIPLUS S7-1200 CPU 1215FC DC/DC/DC (6AG1215-1AF40-5XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1212C DC/DC/DC (6ES7212-1AE40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1212C DC/DC/Rly (6ES7212-1HE40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1212FC DC/DC/DC (6ES7212-1AF40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1212FC DC/DC/Rly (6ES7212-1HF40-0XB0): Versions prior to V4.7
- SIMATIC S7-1200 CPU 1214C AC/DC/Rly (6ES7214-1BG40-0XB0): Versions prior to V4.7

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **CROSS-SITE REQUEST FORGERY (CSRF) CWE-352**

The web interface of the affected devices is vulnerable to cross-site request forgery (CSRF) attacks. This could allow an unauthenticated attacker to change the CPU mode by tricking a legitimate and authenticated user with sufficient permissions on the target CPU to click on a malicious link.

CVE-2024-47100 has been assigned to this vulnerability. A CVSS v3 base score of 7.1 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:R/S:U/C:N/I:L/A:H).

A CVSS v4 score has also been calculated for CVE-2024-47100. A base score of 7.2 has been calculated; the CVSS vector string is (CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:P/VC:N/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Germany

### 3.4 RESEARCHER

David Henrique Estevam de Andrade reported this vulnerability to Siemens.

## 4\. MITIGATIONS

Siemens has released new versions for the affected products and recommends updating to the latest versions:

- SIMATIC S7-1200 CPU: Update to V4.7 or later version.
- SIPLUS S7-1200 CPU: Update to V4.7 or later version.

Siemens has identified the following specific workarounds and mitigations users can apply to reduce risk:

- Do not click on links from untrusted sources.

As a general security measure, Siemens recommends protecting network access to devices with appropriate mechanisms. To operate the devices in a protected IT environment, Siemens recommends configuring the environment according to Siemens' operational guidelines for industrial security and following recommendations in the product manuals.

Additional information on industrial security by Siemens can be found on the Siemens industrial security webpage

For more information see the associated Siemens security advisory SSA-717113 in HTML and CSAF.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability. CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

CISA also recommends users take the following measures to protect themselves from social engineering attacks:

- Refer to Recognizing and Avoiding Email Scams for more information on avoiding email scams.
- Refer to Avoiding Social Engineering and Phishing Attacks for more information on social engineering attacks.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- January 21, 2025: Initial Publication

Go to Source
