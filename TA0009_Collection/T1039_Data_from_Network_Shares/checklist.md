# T1039 – Data from Network Shares

## 🎯 Objective
Collect sensitive files from shared drives or repositories.

---

### 🧰 Tools
net use \\fileserver\share, PowerView `Get-NetShare`, SMBclient, linPEAS.

---

### ✅ Checklist
1. Enumerate open shares (`net view /domain`).  
2. Mount and browse shares.  
3. Collect only targeted directories (finance, HR, R&D).  
4. Compress and stage results.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Sysmon 3 / 5156 | new‑share access from non‑mapped system |
| Zeek smb_files.log | high volume read per file share |
| Sigma | `network_share_enumeration.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

