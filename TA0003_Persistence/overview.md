# TA0003 – Persistence
> **Goal:** Maintain access to a compromised environment across reboots, credential resets, or power cycles.

---

### Core TTPs
| Technique ID | Description | Platforms | Common Tools |
|---------------|--------------|-----------|---------------|
| T1053 | Scheduled Task / Cron | Win / Linux | schtasks, crontab |
| T1547 | Autostart Execution | Win / Linux | reg keys, startup paths, systemd |
| T1050 | New Service | Win / Linux | sc.exe, systemctl |
| T1136 | Create Account | Win / Linux / AD | net user, dsadd, useradd |
| T1543 | Create or Modify System Process | Win / Linux | svchost, systemd |
| T1501 | Web Shell Persistence | Web servers | cmd.aspx, php reverse shells |
| T1556 | Credential Manipulation | Win / AD | mimikatz, lsainject, keymgr.dll |

---

### 🧭 Operational Guidance
- Use **living‑off‑the‑land** binaries (LOLBAS) for stealth.  
- Favor userland or registry‑based persistence to avoid elevated logging.  
- Maintain cleanup scripts (`remove‑persistence.ps1`|`bash_uninstall.sh`).


Author : yasinabedini
GitHub : https://github.com/yasinabedini

