# TA0009 – Collection

> **Objective:** Gather local or remote data of interest (documents, credentials, emails, logs) prior to exfiltration.

---

### 🎯 Primary Targets
| Technique ID | Technique | Description | Platform |
|---------------|------------|-------------|-----------|
| T1005 | Data from Local System | Copy or collect local files (e.g., `.docx`, `.xls`, `.pst`) | Win / Lin |
| T1039 | Data from Network Shares | Collect files over SMB/NFS | Win / Lin |
| T1056 | Input Capture | Keylogging or clipboard capture | Win |
| T1119 | Automated Collection | Scripted gathering of data | All |
| T1114 | Email Collection | Extract mailbox data (Outlook, Exchange, IMAP) | Win / Cloud |
| T1530 | Cloud Storage Collection | Access data from synced or cloud drives (O365, Google Drive) | All |
| T1123 | Audio/Video Capture | Monitor microphone, camera feeds | Win |

---

### 🧩 Operator Notes
- Prefer native OS utilities first (`xcopy`, `robocopy`, `scp`) before dropping third‑party tools.  
- Filter by extension/type using regex to avoid noisy volume copying.  
- Always record hashes of collected files for traceability.  
- Compress collections (7z, rar -sfx, tar.gz) and encrypt before staging.

---

### ⚕ Blue‑Team Perspective
- Large sequential file reads (Sysmon ID 15 + 4663) from *.docx/.xls paths.  
- Unusual access to PST, OST or Share drives.  
- PowerShell scripts invoking file enumeration across drives.


Author : yasinabedini
GitHub : https://github.com/yasinabedini

