---
title: "Trimble Cityworks"
date: 2025-02-06
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v4 8.6**
- **ATTENTION**: Exploitable remotely/low attack complexity/known public exploitation
- **Vendor**: Trimble
- **Equipment**: Cityworks
- **Vulnerability**: Deserialization of Untrusted Data

## 2\. RISK EVALUATION

Successful exploitation of this vulnerability could allow an authenticated user to perform a remote code execution.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

The following versions of Trimble Cityworks, an asset and work management system, are affected:

- Cityworks: All versions prior to 15.8.9
- Cityworks with office companion: All versions prior to 23.10

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **DESERIALIZATION OF UNTRUSTED DATA CWE-502**

Trimble Cityworks versions prior to 15.8.9 and Cityworks with office companion versions prior to 23.10 are vulnerable to a deserialization vulnerability. This could allow an authenticated user to perform a remote code execution attack against a customer's Microsoft Internet Information Services (IIS) web server.

CVE-2025-0994 has been assigned to this vulnerability. A CVSS v3.1 base score of 7.2 has been calculated; the CVSS vector string is (AV:N/AC:L/PR:H/UI:N/S:U/C:H/I:H/A:H).

A CVSS v4 score has also been calculated for CVE-2025-0994. A base score of 8.6 has been calculated; the CVSS vector string is (AV:N/AC:L/AT:N/PR:H/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:**
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** United States

### 3.4 RESEARCHER

Trimble reported this vulnerability to CISA.

## 4\. MITIGATIONS

Cityworks has released the following update guidance for users:

- Trimble will be releasing updated versions to both 15.x (15.8.9 available January 28, 2025) and Cityworks 23.x software releases (23.10 available January 29, 2025). Information on the updated versions will be available through the normal channels via the Cityworks Support Portal(Login required). On-premise customers should install the updated version immediately. These updates will be automatically applied to all Cityworks Online (CWOL) deployments.
- Trimble has observed that some on-premise deployments may have overprivileged Internet Information Services (IIS) identity permissions. For avoidance of doubt, and in accordance with Trimble's technical documentation, IIS should not be run with local or domain level administrative privileges on any site. Please refer to the direction in the latest release notes in the Cityworks Support Portal(Login required) for more information on how to update IIS identity permissions. Trimble's CWOL customers have their IIS identity permissions set appropriately and do not need to take this action.
- Trimble has observed that some deployments have inappropriate attachment directory configurations. Trimble recommends that attachment directory root configuration should be limited to folders/subfolders which only contain attachments. Please refer to the direction in the latest release notes in the Cityworks Support Portal(Login required) for more information on how to ensure proper configuration of the attachment directory.

For more information, see Trimble's notification.

Cityworks software is incapable of controlling industrial processes, and is not directly part of an ICS.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov/ics. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov/ics in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

CISA also recommends users take the following measures to protect themselves from social engineering attacks:

- Do not click web links or open attachments in unsolicited email messages.
- Refer to Recognizing and Avoiding Email Scams for more information on avoiding email scams.
- Refer to Avoiding Social Engineering and Phishing Attacks for more information on social engineering attacks.

CISA has received reports of this vulnerability being actively exploited.

## 5\. UPDATE HISTORY

- February 06, 2025: Initial Publication

Go to Source
