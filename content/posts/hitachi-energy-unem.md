---
title: "Hitachi Energy UNEM"
date: 2025-02-01
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v3 10.0**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: Hitachi Energy
- **Equipment**: UNEM
- **Vulnerabilities**: Authentication Bypass Using an Alternate Path or Channel, Argument Injection, Heap-based Buffer Overflow, Improper Certificate Validation, Use of Hard-coded Password, Improper Restriction of Excessive Authentication Attempts, Cleartext Storage of Sensitive Information, Incorrect User Management

## 2\. RISK EVALUATION

Successful exploitation of these vulnerabilities could allow an attacker to cause a denial of service, execute unintended commands, access sensitive information, or execute arbitrary code.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

Hitachi Energy reports that the following products are affected:

- UNEM: Versions R15A and prior
- UNEM: R15B (CVE-2024-28022, CVE-2024-28024, CVE-2024-28020)
- UNEM: R15B PC4 (CVE-2024-2013, CVE-2024-2012, CVE-2024-2011, CVE-2024-28021, CVE-2024-28023)
- UNEM: R16A
- UNEM: R16B (CVE-2024-28022, CVE-2024-28024, CVE-2024-28020)
- UNEM: R16B PC2 (CVE-2024-2013, CVE-2024-2012, CVE-2024-2011, CVE-2024-28021, CVE-2024-28023)

### 3.2 Vulnerability Overview

#### **3.2.1** **AUTHENTICATION BYPASS USING AN ALTERNATE PATH OR CHANNEL CWE-288**

An authentication bypass vulnerability exists in the UNEM server / APIGateway component that if exploited allows unauthenticated malicious users to interact with the services and the post-authentication attack surface.

CVE-2024-2013 has been assigned to this vulnerability. A CVSS v3 base score of 10.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H).

#### **3.2.2** **IMPROPER NEUTRALIZATION OF ARGUMENT DELIMITERS IN A COMMAND ('ARGUMENT INJECTION') CWE-88**

A vulnerability exists in the UNEM server / APIGateway that if exploited could be used to allow unintended commands or code to be executed on the UNEM server.

CVE-2024-2012 has been assigned to this vulnerability. A CVSS v3 base score of 9.1 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:H/UI:N/S:C/C:H/I:H/A:H).

#### **3.2.3** **HEAP-BASED BUFFER OVERFLOW CWE-122**

A heap-based buffer overflow vulnerability exists in the UNEM that if exploited will generally lead to a denial of service but can be used to execute arbitrary code which is usually outside the scope of a program's implicit security policy.

CVE-2024-2011 has been assigned to this vulnerability. A CVSS v3 base score of 8.6 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:L/I:L/A:H).

#### **3.2.4** **IMPROPER CERTIFICATE VALIDATION CWE-295**

A vulnerability exists in the UNEM server / APIGateway that if exploited could be used to allow unintended commands or code to be executed on the UNEM server.

CVE-2024-28021 has been assigned to this vulnerability. A CVSS v3 base score of 8.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:A/AC:H/PR:N/UI:N/S:C/C:H/I:H/A:N).

#### **3.2.5** **USE OF HARD-CODED PASSWORD CWE-259**

A vulnerability exists in the message queueing mechanism that if exploited can lead to the exposure of resources or functionality to unintended actors, possibly providing malicious users with sensitive information or even execute arbitrary code.

CVE-2024-28023 has been assigned to this vulnerability. A CVSS v3 base score of 5.7 has been assigned; the CVSS vector string is (CVSS:3.1/AV:L/AC:L/PR:H/UI:N/S:C/C:L/I:L/A:L).

#### **3.2.6** **IMPROPER RESTRICTION OF EXCESSIVE AUTHENTICATION ATTEMPTS CWE-307**

A vulnerability exists in the UNEM server / APIGateway that if exploited allows a malicious user to perform an arbitrary number of authentication attempts using different passwords, and eventually gain access to the targeted account.

CVE-2024-28022 has been assigned to this vulnerability. A CVSS v3 base score of 6.5 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:H/PR:N/UI:N/S:C/C:L/I:L/A:L).

#### **3.2.7** **CLEARTEXT STORAGE OF SENSITIVE INFORMATION CWE-312**

A vulnerability exists in the UNEM in which sensitive information is stored in cleartext within a resource that might be accessible to another control sphere.

CVE-2024-28024 has been assigned to this vulnerability. A CVSS v3 base score of 1.9 has been assigned; the CVSS vector string is (CVSS:3.1/AV:L/AC:H/PR:H/UI:N/S:U/C:L/I:N/A:N).

#### **3.2.8** **INCORRECT USER MANAGEMENT CWE-286**

A user/password reuse vulnerability exists in the UNEM application and server management. If exploited a malicious user could use the passwords and login information to extend access on the server and other services.

CVE-2024-28020 has been assigned to this vulnerability. A CVSS v3 base score of 8.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:H/PR:H/UI:N/S:C/C:H/I:H/A:H).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Switzerland

### 3.4 RESEARCHER

Hitachi Energy PSIRT reported these vulnerabilities to CISA.

## 4\. MITIGATIONS

Hitachi Energy has identified the following specific workarounds and mitigations users can apply to reduce risk:

- UNEM R16A, UNEM R15A, UNEM older than R15A: EOL versions - no remediation will be available. Recommended to update to UNEM R16B PC4 or R15B PC5 (update planned) and apply general mitigation factors.
- (CVE-2024-2013, CVE-2024-2012, CVE-2024-28021, CVE-2024-28023) UNEM R16B PC2: Fixed in UNEM R16B PC3 Recommended to update to UNEM R16B PC4 and apply general mitigation factors.
- (CVE-2024-2013, CVE-2024-2012, CVE-2024-2011, CVE-2024-28021, CVE-2024-28023) UNEM R15B PC4: Update to UNEM R15B PC5 (under development) and apply general mitigation factors.
- (CVE-2024-2011) UNEM R16B PC2: Fixed in UNEM R16B PC3 Recommended to update to UNEM R16B PC4 and apply general mitigation factors.
- (CVE-2024-28022, CVE-2024-28024) UNEM R16B, UNEM R15B: Apply general mitigation factors
- (CVE-2024-28020) UNEM R16B, UNEM R15B: Deny nemadm account for ssh logins by configuring DenyUsers in /etc/ssh/sshd\_config

Hitachi Energy recommends users implementing recommended security practices and firewall configurations to help protect the process control network from attacks originating from outside the network. Process control systems should be physically protected from direct access by unauthorized personnel, have no direct connections to the Internet, and be separated from other networks by means of a firewall system with a minimal number of ports exposed. Process control systems should not be used for Internet surfing, instant messaging, or receiving e-mails. Portable computers and removable storage media should be carefully scanned for viruses before they are connected to a control system.

For more information, see Hitachi Energy Cybersecurity Advisory "Multiple Vulnerabilities in Hitachi Energy's UNEM".

CISA recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities, such as:

- When remote access is required, use more secure methods, such as virtual private networks (VPNs). Recognize VPNs may have vulnerabilities, should be updated to the most recent version available, and are only as secure as the connected devices.

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures.

CISA also provides a section for control systems security recommended practices on the ICS webpage on cisa.gov. Several CISA products detailing cyber defense best practices are available for reading and download, including Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies.

CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

Additional mitigation guidance and recommended practices are publicly available on the ICS webpage at cisa.gov in the technical information paper, ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies.

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

CISA also recommends users take the following measures to protect themselves from social engineering attacks:

- Do not click web links or open attachments in unsolicited email messages.
- Refer to Recognizing and Avoiding Email Scams for more information on avoiding email scams.
- Refer to Avoiding Social Engineering and Phishing Attacks for more information on social engineering attacks.

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

## 5\. UPDATE HISTORY

- January 30, 2025: Initial Publication

Go to Source
