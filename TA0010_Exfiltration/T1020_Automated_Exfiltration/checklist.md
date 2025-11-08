# T1020 – Automated Exfiltration

## 🎯 Objective
Automate data uploads at interval to minimize operator exposure.

---

### 🧰 Approach
PowerShell loop with Invoke‑WebRequest, CRON scp tasks, custom agent.

---

### ✅ Checklist
1. Implement interval timer (1 MB every 60 s).  
2. Compress & timestamp files.  
3. Use checksum validation.  
4. Cleanup old archives.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Sysmon 1 + TaskScheduler | repeated scheduled network uploads |
| Sigma | `automated_exfil.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

