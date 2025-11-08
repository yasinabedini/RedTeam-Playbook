# T1562 – Impair Defenses

## 🎯 Objective
Disable or evade security controls such as antivirus, EDR, and audit logging.

---

### 🧰 Tools
- Windows: `net stop Windefend`, PowerShell Set‑MpPreference, TamperDefender, Disable‑SecurityCenter.ps1  
- Linux: `systemctl stop auditd`, modifying /etc/rsyslog.conf  
- Universal: AMSI patch + ETW patch via inline assembly (e.g., `0x75 → 0xEB`)

---

### ✅ Checklist
| Step | Action | Example |
|------|---------|----------|
| 1 | Check Defender status | `Get‑MpComputerStatus` |
| 2 | Disable AV/EDR component | `sc stop WdNisSvc` |
| 3 | Patch AMSI/ETW | DLL pattern patch |
| 4 | Verify logs stopped | `wevtutil qe Microsoft‑Windows‑PowerShell/Operational /q:*` |
| 5 | Re‑enable after test |

---

### ⚕ Detection
| Source | Indicator |
|---------|------------|
| Sysmon | service stop (7036), driver delete |
| PowerShell Logs | 4103 / 4104 – Set‑MpPreference invocation |
| Sigma | `defender_disable.yml`, `amsi_patch_detect.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

