---
title: "Siemens User Management Component"
date: 2025-01-02
categories: 
  - "security"
---

As of January 10, 2023, CISA will no longer be updating ICS security advisories for Siemens product vulnerabilities beyond the initial advisory. For the most up-to-date information on vulnerabilities in this advisory, see Siemens' ProductCERT Security Advisories (CERT Services | Services | Siemens Global).

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 9.3**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Siemens
- **Equipment**: User Management Component (UMC)
- **Vulnerability**: Heap-based Buffer Overflow

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an unauthenticated remote attacker arbitrary code execution.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Siemens reports the following products are affected:

- Opcenter Execution Foundation: All versions
- Opcenter Intelligence: All versions
- Opcenter Quality: All versions
- Opcenter RDL: All versions
- SIMATIC PCS neo V4.0: All versions
- SIMATIC PCS neo V4.1: All versions
- SIMATIC PCS neo V5.0: All versions prior to V5.0 Update 1
- SINEC NMS: All versions
- Totally Integrated Automation Portal (TIA Portal) V16: All versions
- Totally Integrated Automation Portal (TIA Portal) V17: All versions
- Totally Integrated Automation Portal (TIA Portal) V18: All versions
- Totally Integrated Automation Portal (TIA Portal) V19: All versions

### 3.2 Vulnerability Overview

#### **3.2.1** **HEAP-BASED BUFFER OVERFLOW CWE-122**

Affected products contain a heap-based buffer overflow vulnerability in the integrated UMC component. This could allow an unauthenticated remote attacker to execute arbitrary code.

CVE-2024-49775 has been assigned to this vulnerability. A CVSS v3 base score of 9.8 has been calculated; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2024-49775. A base score of 9.3 has been calculated; the CVSS vector string is (CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Germany

### 3.4 RESEARCHER

Tenable reported this vulnerability to Siemens.

## 4\. MITIGATIONS

Siemens has released new versions for several affected products and recommends updating to the latest versions. Siemens is preparing further fix versions and recommends countermeasures for products where fixes are not, or are not yet, available.

- SIMATIC PCS neo V5.0: Update to V5.0 Update 1 or later version
- SINEC NMS: Update SINEC NMS to V3.0 SP2 or later version and UMC to V2.15 or later version. Contact customer support to receive patch and update information.

Siemens has identified the following specific workarounds and mitigations users can apply to reduce risk:

- Filter the Ports 4002 and 4004 to only accept connections to/from the IP addresses of machines that run UMC and are part of the UMC network e.g. with an external firewall
- In addition if no RT server machines are used, Port 4004 can be blocked completely.

As a general security measure, Siemens recommends protecting network access to devices with appropriate mechanisms. To operate the devices in a protected IT environment, Siemens recommends configuring the environment according to Siemens' operational guidelines for industrial security and following recommendations in the product manuals.

Additional information on industrial security by Siemens can be found on the Siemens industrial security webpage.

For more information see the associated Siemens security advisory SSA-928984 in HTML and CSAF.

CISA recommends users take defensive measures to minimize the risk of exploitation of this vulnerability. CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting this vulnerability has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- December 19, 2024: Initial Publication
