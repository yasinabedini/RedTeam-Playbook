# T1119 – Automated Collection

## 🎯 Objective
Script and automate gathering of data across hosts or user profiles.

---

### 🧰 Methods
- PowerShell: `Get‑ChildItem ‑Recurse ‑Include *.docx,*.xls*`  
- Python: os.walk / shutil.copy2()  

---

### ✅ Checklist
1. Build inclusion filters.  
2. Automate zipping and metadata logging.  
3. Schedule collection via Task or CRON.  
4. Encrypt archives.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Sysmon 1 + 11 | Recurring script repeating file access |
| Sigma | `automated_file_collection.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

