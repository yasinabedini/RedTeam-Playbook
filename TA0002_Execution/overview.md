# TA0002 – Execution
> **Goal:** Execute adversary-controlled code, scripts, or binaries on targeted systems to achieve persistence or lateral movement.

---

## 🧭 Core Objective
To transition from initial foothold to active control by executing commands, payloads, and scripts on both Windows and Linux environments.

---

### Execution Vectors
| Technique ID | Name | OS | Common Tools |
|---------------|------|----|---------------|
| T1059 | Command & Scripting Interpreter | Win / Linux | PowerShell, Bash, Python |
| T1047 | Windows Management Instrumentation | Windows | wmic, wmi-class, Impacket |
| T1569 | Service Execution | Windows / Linux | sc.exe, systemctl |
| T1053 | Scheduled Task / Cron | Win / Linux | schtasks, crontab |
| T1203 | Exploitation for Execution | Win / Linux | Metasploit, ExploitDB |
| T1028 | Windows Remote Management (WinRM) | Windows | Evil-WinRM, PowerShell remoting |

---

## ⚙️ Operational Advice
- Maintain execution transparency (mimic trusted binaries: `msbuild.exe`, `rundll32.exe`)
- Prefer in-memory loaders to evade AM/EDR
- Monitor audit policy on Linux (`auditd`, `journald`) for local privilege escalation testing


Author : yasinabedini
GitHub : https://github.com/yasinabedini

