---
title: "ABB ASPECT-Enterprise, NEXUS, and MATRIX Series Products"
date: 2025-01-08
categories: 
  - "cisa"
  - "cybersecurity"
  - "security"
---

**View CSAF**

## 1\. EXECUTIVE SUMMARY

- **CVSS v3 10.0**
- **ATTENTION**: Exploitable remotely/low attack complexity
- **Vendor**: ABB
- **Equipment**: ASPECT-Enterprise, NEXUS, and MATRIX series
- **Vulnerabilities**: Files or Directories Accessible to External Parties, Improper Validation of Specified Type of Input, Cleartext Transmission of Sensitive Information, Cross-site Scripting, Server-Side Request Forgery (SSRF), Improper Neutralization of Special Elements in Data Query Logic, Allocation of Resources Without Limits or Throttling, Weak Password Requirements, Cross-Site Request Forgery (CSRF), Use of Weak Hash, Code Injection, PHP Remote File Inclusion, External Control of System or Configuration Setting, Insufficiently Protected Credentials, Unrestricted Upload of File with Dangerous Type, Absolute Path Traversal, Use of Default Credentials, Off-by-one Error, Use of Default Password, Session Fixation

## 2\. RISK EVALUATION

Multiple vulnerabilities in ABB ASPECT-Enterprise, NEXUS, and MATRIX series products have been reported, which could enable an attacker to disrupt operations or execute remote code.

## 3\. TECHNICAL DETAILS

### 3.1 AFFECTED PRODUCTS

ABB reports the following products are affected:

- ABB NEXUS Series: NEXUS-3-x <=3.08.02 (CVE-2024-6515, CVE-2024-6516, CVE-2024-6784, CVE-2024-48843, CVE-2024-48844, CVE-2024-48846, CVE-2024-48839, CVE-2024-48840, CVE-2024-51541, CVE-2024-51542, CVE-2024-51543, CVE-2024-51544, CVE-2024-51545, CVE-2024-51546, CVE-2024-51548, CVE-2024-51549, CVE-2024-51550, CVE-2024-51554, CVE-2024-11316, CVE-2024-11317)
- ABB NEXUS Series: NEX-2x <=3.07.02 (CVE-2024-48845, CVE-2024-51551, CVE-2024-51555)
- ABB NEXUS Series: NEX-2x <=3.08.02 (CVE-2024-6515, CVE-2024-6516, CVE-2024-6784, CVE-2024-48843, CVE-2024-48844, CVE-2024-48846, CVE-2024-48839, CVE-2024-48840, CVE-2024-51541, CVE-2024-51542, CVE-2024-51543, CVE-2024-51544, CVE-2024-51545, CVE-2024-51546, CVE-2024-51548, CVE-2024-51549, CVE-2024-51550, CVE-2024-51554, CVE-2024-11316, CVE-2024-11317)
- ABB NEXUS Series: NEXUS-3-x <=3.08.01 (CVE-2024-6209, CVE-2024-6298, CVE-2024-48847)
- ABB ASPECT-Enterprise: ASP-ENT-x <=3.08.02 (CVE-2024-6515, CVE-2024-6516, CVE-2024-6784, CVE-2024-48843, CVE-2024-48844, CVE-2024-48846, CVE-2024-48839, CVE-2024-48840, CVE-2024-51541, CVE-2024-51542, CVE-2024-51543, CVE-2024-51544, CVE-2024-51545, CVE-2024-51546, CVE-2024-51548, CVE-2024-51549, CVE-2024-51550, CVE-2024-51554, CVE-2024-11316, CVE-2024-11317)
- ABB MATRIX Series: MAT-x <=3.08.02 (CVE-2024-6515, CVE-2024-6516, CVE-2024-6784, CVE-2024-48843, CVE-2024-48844, CVE-2024-48846, CVE-2024-48839, CVE-2024-48840, CVE-2024-51541, CVE-2024-51542, CVE-2024-51543, CVE-2024-51544, CVE-2024-51545, CVE-2024-51546, CVE-2024-51548, CVE-2024-51549, CVE-2024-51550, CVE-2024-51554, CVE-2024-11316, CVE-2024-11317)
- ABB MATRIX Series: MAT-x <=3.08.01 (CVE-2024-6209, CVE-2024-6298, CVE-2024-48847)
- ABB MATRIX Series: MAT-x <=3.07.02 (CVE-2024-48845, CVE-2024-51551, CVE-2024-51555)
- ABB ASPECT-Enterprise: ASP-ENT-x <=3.08.01 (CVE-2024-6209, CVE-2024-6298, CVE-2024-48847)
- ABB ASPECT-Enterprise: ASP-ENT-x <=3.07.02 (CVE-2024-48845, CVE-2024-51551, CVE-2024-51555)
- ABB NEXUS Series: NEX-2x <=3.08.01 (CVE-2024-6209, CVE-2024-6298, CVE-2024-48847)
- ABB NEXUS Series: NEXUS-3-x <=3.07.02 (CVE-2024-48845, CVE-2024-51551, CVE-2024-51555)

### 3.2 VULNERABILITY OVERVIEW

#### **3.2.1** **FILES OR DIRECTORIES ACCESSIBLE TO EXTERNAL PARTIES CWE-552**

Unauthorized file access in WEB Server in ASPECT versions 3.08.01 and prior allow an attacker to access files unauthorized.

CVE-2024-6209 has been assigned to this vulnerability. A CVSS v3 base score of 10.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H).

#### **3.2.2** **IMPROPER VALIDATION OF SPECIFIED TYPE OF INPUT CWE-1287**

An improper input validation vulnerability in ASPECT allows remote code inclusion.

CVE-2024-6298 has been assigned to this vulnerability. A CVSS v3 base score of 10.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H).

#### **3.2.3** **CLEARTEXT TRANSMISSION OF SENSITIVE INFORMATION CWE-319**

Web browser interface may manipulate application username/password in clear text or Base64 encoding in ABB ASPECT providing a higher probability of unintended credentials exposure.

CVE-2024-6515 has been assigned to this vulnerability. A CVSS v3 base score of 9.6 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:C/C:H/I:H/A:N).

#### **3.2.4** **IMPROPER NEUTRALIZATION OF INPUT DURING WEB PAGE GENERATION ('CROSS-SITE SCRIPTING') CWE-79**

A cross-site scripting vulnerability was found in ABB ASPECT providing a potential for malicious scripts to be injected into a client browser.

CVE-2024-6516 has been assigned to this vulnerability. A CVSS v3 base score of 9.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:H/UI:N/S:C/C:H/I:H/A:L).

#### **3.2.5** **SERVER-SIDE REQUEST FORGERY (SSRF) CWE-918**

A server-side request forgery vulnerability was found in ASPECT providing a potential for access to unauthorized resources and unintended information disclosure.

CVE-2024-6784 has been assigned to this vulnerability. A CVSS v3 base score of 9.9 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:C/C:H/I:H/A:H).

#### **3.2.6** **IMPROPER NEUTRALIZATION OF SPECIAL ELEMENTS IN DATA QUERY LOGIC CWE-943**

A SQL injection vulnerability was found in ASPECT providing a potential for unintended information disclosure.

CVE-2024-48843 has been assigned to this vulnerability. A CVSS v3 base score of 8.2 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:H/PR:L/UI:N/S:C/C:H/I:H/A:N).

#### **3.2.7** **ALLOCATION OF RESOURCES WITHOUT LIMITS OR THROTTLING CWE-770**

A denial of service vulnerability was found in ASPECT providing a potential for device service disruptions.

CVE-2024-48844 has been assigned to this vulnerability. A CVSS v3 base score of 7.7 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:H/PR:L/UI:N/S:C/C:L/I:L/A:H).

#### **3.2.8** **WEAK PASSWORD REQUIREMENTS CWE-521**

A weak password reset rules vulnerability was found in ASPECT providing a potential for the storage of weak passwords that could facilitate unauthorized admin/application access.

CVE-2024-48845 has been assigned to this vulnerability. A CVSS v3 base score of 9.4 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:L).

#### **3.2.9** **CROSS-SITE REQUEST FORGERY (CSRF) CWE-352**

A cross site request forgery vulnerability was found in ASPECT providing a potential for exposing sensitive information or changing system settings.

CVE-2024-48846 has been assigned to this vulnerability. A CVSS v3 base score of 7.1 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:U/C:L/I:H/A:N).

#### **3.2.10.0** **USE OF WEAK HASH CWE-328**

A MD5 checksum bypass vulnerability was found in ASPECT exploiting a weakness in the way an application dependency calculates or validates MD5 checksum hashes.

CVE-2024-48847 has been assigned to this vulnerability. A CVSS v3 base score of 8.2 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:L/I:H/A:N).

#### **3.2.11** **IMPROPER CONTROL OF GENERATION OF CODE ('CODE INJECTION') CWE-94**

An improper input validation vulnerability in ASPECT allows remote code execution.

CVE-2024-48839 has been assigned to this vulnerability. A CVSS v3 base score of 10.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:L).

#### **3.2.12** **IMPROPER CONTROL OF GENERATION OF CODE ('CODE INJECTION') CWE-94**

An unauthorized access vulnerability in ASPECT allows remote code execution.

CVE-2024-48840 has been assigned to this vulnerability. A CVSS v3 base score of 10.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:L).

#### **3.2.13** **IMPROPER CONTROL OF FILENAME FOR INCLUDE/REQUIRE STATEMENT IN PHP PROGRAM ('PHP REMOTE FILE INCLUSION') CWE-98**

A local file inclusion vulnerability in ASPECT allows access to sensitive system information.

CVE-2024-51541 has been assigned to this vulnerability. A CVSS v3 base score of 8.2 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:L/A:N).

#### **3.2.14** **FILES OR DIRECTORIES ACCESSIBLE TO EXTERNAL PARTIES CWE-552**

A configuration download vulnerability in ASPECT allows access to dependency configuration information.

CVE-2024-51542 has been assigned to this vulnerability. A CVSS v3 base score of 8.2 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:L/A:N).

#### **3.2.15** **EXTERNAL CONTROL OF SYSTEM OR CONFIGURATION SETTING CWE-15**

An information disclosure vulnerability in ASPECT allows access to application configuration information.

CVE-2024-51543 has been assigned to this vulnerability. A CVSS v3 base score of 8.2 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:L/A:N).

#### **3.2.16** **EXTERNAL CONTROL OF SYSTEM OR CONFIGURATION SETTING CWE-15**

A service control vulnerability in ASPECT allows access to service restart requests and vm configuration settings.

CVE-2024-51544 has been assigned to this vulnerability. A CVSS v3 base score of 8.2 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:N/I:L/A:H).

#### **3.2.17** **INSUFFICIENTLY PROTECTED CREDENTIALS CWE-522**

An username enumeration vulnerability in ASPECT allows access to application level username add, delete, modify and list functions.

CVE-2024-51545 has been assigned to this vulnerability. A CVSS v3 base score of 10.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H).

#### **3.2.18** **IMPROPER VALIDATION OF SPECIFIED TYPE OF INPUT CWE-1287**

A credentials disclosure vulnerability in ASPECT allow access to on board project backup bundles.

CVE-2024-51546 has been assigned to this vulnerability. A CVSS v3 base score of 7.5 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N).

#### **3.2.19** **UNRESTRICTED UPLOAD OF FILE WITH DANGEROUS TYPE CWE-434**

A dangerous file upload vulnerability in ASPECT allows upload of malicious scripts.

CVE-2024-51548 has been assigned to this vulnerability. A CVSS v3 base score of 9.9 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:C/C:H/I:H/A:H).

#### **3.2.20** **ABSOLUTE PATH TRAVERSAL CWE-36**

An absolute file traversal vulnerability in ASPECT allows access and modification of unintended resources.

CVE-2024-51549 has been assigned to this vulnerability. A CVSS v3 base score of 10.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:L).

#### **3.2.21** **IMPROPER VALIDATION OF SPECIFIED TYPE OF INPUT CWE-1287**

A data validation / data sanitization vulnerability in ASPECT Linux allows unvalidated and unsanitized data to be injected in an ASPECT device.

CVE-2024-51550 has been assigned to this vulnerability. A CVSS v3 base score of 10.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:L).

#### **3.2.22** **USE OF DEFAULT CREDENTIALS CWE-1392**

A default credential vulnerability in ASPECT on Linux allows access to an ASPECT device using publicly available default credentials.

CVE-2024-51551 has been assigned to this vulnerability. A CVSS v3 base score of 10.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H).

#### **3.2.23** **OFF-BY-ONE ERROR CWE-193**

An off by one error vulnerability in ASPECT allow an array out of bounds condition in a log script.

CVE-2024-51554 has been assigned to this vulnerability. A CVSS v3 base score of 9.1 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:C/C:H/I:L/A:L).

#### **3.2.24** **USE OF DEFAULT PASSWORD CWE-1393**

Default credential vulnerability in ASPECT allows access to an ASPECT device using publicly available default credentials, since the system does not require the installer to change default credentials.

CVE-2024-51555 has been assigned to this vulnerability. A CVSS v3 base score of 10.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H).

#### **3.2.25** **ALLOCATION OF RESOURCES WITHOUT LIMITS OR THROTTLING CWE-770**

A filesize check vulnerability in ASPECT allow a malicious user to bypass size limits or overload an ASPECT device.

CVE-2024-11316 has been assigned to this vulnerability. A CVSS v3 base score of 7.5 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:N/I:N/A:H).

#### **3.2.26** **SESSION FIXATION CWE-384**

Session fixation vulnerability in ASPECT allow an attacker to fix a user's session identifier before login providing an opportunity for session takeover on an ASPECT device.

CVE-2024-11317 has been assigned to this vulnerability. A CVSS v3 base score of 10.0 has been assigned; the CVSS vector string is (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:N).

### 3.3 BACKGROUND

- **CRITICAL INFRASTRUCTURE SECTORS:** Critical Manufacturing
- **COUNTRIES/AREAS DEPLOYED:** Worldwide
- **COMPANY HEADQUARTERS LOCATION:** Switzerland

### 3.4 RESEARCHER

Gjoko Krstikj of Zero Science Lab reported these vulnerabilities to CISA.

## 4\. MITIGATIONS

ABB has identified the following specific workarounds and mitigations users can apply to reduce risk:

- (CVE-2024-6209, CVE-2024-6298, CVE-2024-48847) ASP-ENT-x <=3.08.01, NEX-2x <=3.08.01, MAT-x <=3.08.01, NEXUS-3-x <=3.08.01: The vulnerabilities have been resolved in product versions 3.08.02 and later.
- (CVE-2024-6515, CVE-2024-6516, CVE-2024-6784, CVE-2024-48843, CVE-2024-48844, CVE-2024-48846, CVE-2024-48839, CVE-2024-48840, CVE-2024-51541, CVE-2024-51542, CVE-2024-51543, CVE-2024-51544, CVE-2024-51545, CVE-2024-51546, CVE-2024-51548, CVE-2024-51549, CVE-2024-51550, CVE-2024-51554, CVE-2024-11316, CVE-2024-11317) ASP-ENT-x <=3.08.02, NEX-2x <=3.08.02, NEXUS-3-x <=3.08.02, MAT-x <=3.08.02: The vulnerabilities have been resolved in product versions 3.08.03 and later.
- (CVE-2024-48845) ASP-ENT-x <=3.07.02, NEXUS-3-x <=3.07.02, NEX-2x <=3.07.02, MAT-x <=3.07.02: The vulnerabilities have been resolved in product versions 3.08.00 and later.
- (CVE-2024-51551, CVE-2024-51555) ASP-ENT-x <=3.07.02, NEXUS-3-x <=3.07.02, NEX-2x <=3.07.02, MAT-x <=3.07.02: The vulnerabilities have been resolved in product versions 3.08.00 and later.

CISA recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities, such as:

- Minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the Internet.
- Locate control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs). Recognize VPNs may have vulnerabilities, should be updated to the most recent version available, and are only as secure as the connected devices.

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

- January 7, 2025: Initial Publication

Go to Source
