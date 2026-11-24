# Mediroza General Hospital — Black-Box Penetration Test

**Networkwalks Cybersecurity Internship — Batch B084, Week 4**
**Status:** Completed
**Overall Risk:** 🔴 Critical

> ⚠️ **Disclaimer:** This assessment was performed only against a target explicitly authorised for testing by Networkwalks as part of a supervised internship exercise. All techniques, commands and findings in this repository are documented for educational and internship-assessment purposes only. Do not use any of this against systems you do not own or do not have explicit written permission to test. Unauthorised access to a computer system is a crime in most jurisdictions, even when no damage occurs.

---

## Overview

This repository documents an authorised external black-box web application penetration test against Mediroza General Hospital's web application, carried out as the Week 4 project of the Networkwalks Cybersecurity Internship. The engagement identified an SQL injection authentication bypass on the patient portal, an unauthenticated public database backup, and weak password protection on patient PDF reports, among other issues. Full technical detail, evidence and remediation guidance are in the final report.

## Scope & Target

| Item | Detail |
|---|---|
| Target | `https://medirozahospital.com` |
| Assessment Type | External Black-Box Web Application Penetration Test |
| Testing Environment | Kali Linux, Firefox |
| Permission | Written authorisation granted by Networkwalks |
| Out of Scope | Social engineering, denial-of-service testing, anything outside the target domain |

## Methodology

1. **Reconnaissance** — domain intelligence, web-technology fingerprinting, robots.txt discovery
2. **Scanning & Enumeration** — directory listing review, unauthenticated backup retrieval
3. **Initial Access** — authentication testing and SQL injection exploitation
4. **PDF Password Security** — encryption analysis and offline password recovery
5. **PDF Metadata Analysis** — metadata extraction and correlation with exposed database records

## Tools Used

| Tool | Purpose |
|---|---|
| WHOIS, WhatWeb | Domain intelligence and web-technology fingerprinting |
| cURL, Wget | HTTP inspection, directory discovery, authentication testing and backup retrieval |
| Firefox / Developer Tools | Manual login testing, portal verification and evidence collection |
| grep, awk | Database schema inspection and metadata-to-record correlation |
| Networkwalks Hash Calculator | Extraction of PDF-specific `$pdf$` hashes |
| Networkwalks Password Cracker | Dictionary-based PDF password testing |
| pdf2john, John the Ripper, RockYou | Offline hash extraction and password recovery verification |
| qpdf, ExifTool | Document decryption, encryption checks and metadata examination |

## Key Findings

| ID | Finding | Severity |
|---|---|---|
| M-01 | SQL Injection — Patient Portal Authentication Bypass | 🔴 Critical |
| M-02 | Unauthenticated Database Backup Disclosure | 🟠 High |
| M-03 | Weak Password Protection on Patient PDFs | 🟠 High |
| M-04 | Sensitive PDF Metadata Disclosure | 🟡 Medium |
| M-05 | Username Enumeration | 🟡 Low |
| M-06 | Directory Listing on Legacy Directory | 🟡 Low |

Full proof-of-exploitation, screenshots and remediation steps for each finding are documented in the report.

## Repository Structure

```
├── report/
│   └── Mediroza_Penetration_Testing_Report.docx   # Full pentest report
├── evidence/
│   └── figures/                                   # Screenshots referenced in the report (Figure 01–15)
└── README.md
```

## Report

📄 [`Mediroza_Penetration_Testing_Report_final.pdf`] 

## Author

**kelvin chitauro**
Cybersecurity Intern — Networkwalks, Batch B084
