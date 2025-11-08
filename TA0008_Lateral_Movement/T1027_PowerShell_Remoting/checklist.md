# T1027 (Variant) – PowerShell Remoting

## 🎯 Objective
Use PowerShell Remoting for execution or lateral movement.

### 🧰 Commands
Enable‑PSRemoting, New‑PSSession, Invoke‑Command, Enter‑PSSession.  

### ✅ Checklist
1. Confirm WinRM ports 5985‑5986 reachable.  
2. Configure CredSSP if needed.  
3. Spawn session to target.  
4. Execute post‑exploitation commands.  

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| 4624 Type 3 | Logins via `WinRM` service |
| PowerShell Logs | `New-PSSession` execution |
| Sigma | `psremoting_exec_detect.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

