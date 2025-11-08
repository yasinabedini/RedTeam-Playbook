# T1070 – Indicator Removal on Host

## 🎯 Objective
Clear logs, delete artifacts, and remove forensic traces.

---

### 🧰 Tools
| Platform | Example |
|-----------|----------|
| Windows | `wevtutil cl Security`, `Clear‑EventLog`, `del /b /q` |
| Linux | `history -c`, `shred`, `rm ‑rf /var/log/*` |
| File timestamp edit | `PowerToysTimestomper.py`, `touch ‑r` |

---

### ✅ Checklist
1. Clear PowerShell logs (4104 logs)  
2. Delete temporary payloads (after exfil done)  
3. Wipe prefetch and event logs as last step  
4. Replace timestamps

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Sysmon | event 1 + parent = cmd/powershell executing wevtutil |
| Sigma | `clear_event_logs.yml`, `timestomp_detect.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

