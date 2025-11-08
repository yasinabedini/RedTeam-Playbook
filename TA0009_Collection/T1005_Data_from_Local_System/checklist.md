# T1005 – Data from Local System

## 🎯 Objective
Copy or consolidate files locally for future exfiltration.

---

### 🧰 Tools
| Platform | Tools |
|-----------|-------|
| Windows | robocopy, xcopy, PowerShell Copy‑Item |
| Linux | cp, tar, find + scp |

---

### ✅ Checklist
1. Identify file types: `.docx`, `.xls*`, `.pdf`, `.key`, `.txt`.  
2. Use filters to collect target sets:  
   `robocopy C:\Users D:\stage *.doc* /L /FP /NJH`  
3. Compress output folders (`7z a collect.7z *.docx -p<key>`).  
4. Hash results (MD5/SHA256).  
5. Wipe temporary cache if safe.

---

### ⚕ Detection
| Log Source | Indicator |
|-------------|-----------|
| Sysmon 11 | High volume file access on user dirs |
| Sigma | `bulk_file_copy.yml` |
| EDR | Robocopy execution outside backup accounts |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

