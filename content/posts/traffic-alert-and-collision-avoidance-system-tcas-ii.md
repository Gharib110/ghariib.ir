---
title: "Traffic Alert and Collision Avoidance System (TCAS) II"
date: 2025-01-22
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 7.1**
- **ATTENTION**: Exploitable from adjacent network
- **Standard**: Traffic Alert and Collision Avoidance System (TCAS) II
- **Equipment**: Collision Avoidance Systems
- **Vulnerabilities**: Reliance on Untrusted Inputs in a Security Decision, External Control of System or Configuration Setting

## 2\. RISK EVALUATION

Successful exploitation of these vulnerabilities could allow an attacker to manipulate safety systems and cause a denial-of-service condition.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following revisions of TCAS II are affected:

- TCAS II: Versions 7.1 and prior

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **Reliance on Untrusted Inputs in a Security Decision CWE-807**

By utilizing software-defined radios and a custom low-latency processing pipeline, RF signals with spoofed location data can be transmitted to aircraft targets. This can lead to the appearance of fake aircraft on displays and potentially trigger undesired Resolution Advisories (RAs).

CVE-2024-9310 has been assigned to this vulnerability. A CVSS v3.1 base score of 6.1 has been calculated; the CVSS vector string is (AV:A/AC:H/PR:N/UI:N/S:C/C:N/I:H/A:N).

A CVSS v4 score has also been calculated for CVE-2024-9310. A base score of 6.0 has been calculated; the CVSS vector string is (AV:A/AC:H/AT:P/PR:N/UI:N/VC:N/VI:H/VA:N/SC:N/SI:N/SA:N).

#### **3.2.2** **External Control of System or Configuration Setting CWE-15**

For TCAS II systems using transponders compliant with MOPS earlier than RTCA DO-181F, an attacker can impersonate a ground station and issue a Comm-A Identity Request. This action can set the Sensitivity Level Control (SLC) to the lowest setting and disable the Resolution Advisory (RA), leading to a denial-of-service condition.

CVE-2024-11166 has been assigned to this vulnerability. A CVSS v3.1 base score of 8.2 has been calculated; the CVSS vector string is (AV:A/AC:L/PR:N/UI:N/S:C/C:N/I:L/A:H).

A CVSS v4 score has also been calculated for CVE-2024-11166. A base score of 7.1 has been calculated; the CVSS vector string is (AV:A/AC:L/AT:N/PR:N/UI:N/VC:N/VI:L/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Transportation Systems
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** United States

### 3.4 RESEARCHER

Giacomo Longo and Enrico Russo of Genova University reported these vulnerabilities to CISA.  
Martin Strohmeier and Vincent Lenders of armasuisse reported these vulnerabilities to CISA.  
Alessio Merlo of Centre for High Defense Studies reported these vulnerabilities to CISA.

## 4\. MITIGATIONS

After consulting with the Federal Aviation Administration (FAA) and the researchers regarding these vulnerabilities, it has been concluded that CVE-2024-11166 can be fully mitigated by upgrading to ACAS X or by upgrading the associated transponder to comply with RTCA DO-181F.

Currently, there is no mitigation available for CVE-2024-9310.

These vulnerabilities in the TCAS II standard are exploitable in a lab environment. However, they require very specific conditions to be met and are unlikely to be exploited outside of a lab setting.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time. These vulnerabilities are not exploitable remotely. These vulnerabilities have a high attack complexity.

## 5\. UPDATE HISTORY

- January 21, 2024: Initial Publication

Go to Source
