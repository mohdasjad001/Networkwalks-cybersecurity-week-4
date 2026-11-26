# Week 4 — Black-Box Penetration Test & Vulnerability Assessment (Networkwalks Cybersecurity Internship)

## Overview
This repository documents my completion of the mandatory Week 4 Capstone Project (`W4-PM-FINAL`) for the Networkwalks Cybersecurity Internship (guided by Waqar Karim, CCIE):
- **Target:** `https://medirozahospital.com` (Authorized Training Lab Environment)
- **M1 — Initial Access:** SQL Injection Authentication Bypass on `/patient/login.php` (`admin' -- -`)
- **M2 — Data Extraction:** Offline dictionary attack on 3 encrypted patient pathology PDF reports (`LR-2024-1187`, `LR-2024-1192`, `LR-2024-1205`)
- **M3 — Data Exposure:** Unauthenticated database backup retrieval (`/old/mediroza_db_backup_2019.sql`) and LiteSpeed directory listing (`/staff/`, `/patient/`)
- **M4 — Reporting:** Formal Black-Box Penetration Testing & Vulnerability Assessment Report (`report/Mediroza_Pentest_Report.pdf`)

### Target Findings & Recovered Artifacts
- **F-01 (CRITICAL — SQLi Auth Bypass):** Payload `admin' -- -` bypassed `/patient/login.php` and exposed `/patient/portal.php`
- **F-02 (CRITICAL — Weak PDF Encryption):**
  - `Report 1` (`LR-2024-1187`) → Cracked Password: `123456`
  - `Report 2` (`LR-2024-1192`) → Cracked Password: `password`
  - `Report 3` (`LR-2024-1205`) → Cracked Password: `!@#$%^&`
- **F-03 (CRITICAL — Unauthenticated DB Backup):** `/old/mediroza_db_backup_2019.sql` exposed `mediroza_hr` (`staff`: 30 records; `shareholders`: 10 records / 100% equity)
- **F-04 (HIGH — Directory Listing):** Public indexing enabled on `/staff/` and `/patient/`

## Repository Structure
```text
networkwalks-cybersecurity-week-4/
├── README.md
├── report/
│   └── Mediroza_Pentest_Report.pdf
└── screenshots/
    ├── PDF-1 Password_2.png
    ├── PDF-1 report_2.png
    ├── PDF-2 Password_2.png
    ├── PDF-2 report_2.png
    ├── PDF-3 Password_2.png
    ├── PDF-3 report_2.png
    ├── M3-a_3.png
    ├── M3-b_3.png
    └── M3-c_3.png
