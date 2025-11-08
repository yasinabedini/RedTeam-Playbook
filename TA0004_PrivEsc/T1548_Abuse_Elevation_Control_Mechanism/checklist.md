# T1548 – Abuse Elevation Control Mechanism

## 🎯 Objective
Bypass or abuse UAC/sudo to execute with elevated privileges.

---

### 🧰 Tools
- Windows: UACME, FodHelper, CMSTP, Runas
- Linux: sudo misconfig, LD_PRELOAD, PATH injection

---

### ✅ Checklist
| Step | Action | Example |
|------|---------|----------|
| 1 | Check UAC level | `reg query HKLM\...\ConsentPromptBehaviorAdmin` |
| 2 | Exploit trusted binary (bypass UAC) | UACME method #23 |
| 3 | Linux sudo –l review | `sudo ‑l` |
| 4 | Inject PATH | `echo '/tmp' >> $PATH` |

---

### ⚕ Detection
| Platform | Indicator |
|-----------|-----------|
| Win | event ID 1 + parent = fodhelper.exe / sdclt.exe |
| Lin | auditd sudo exec events |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

