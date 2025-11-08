# T1021 – Remote Services

## 🎯 Objective
Access remote systems using standard administration protocols and obtained credentials.

---

### 🧰 Tools
| Platform | Tools |
|-----------|-------|
| Windows | PsExec, WMIC, PowerShell Remoting |
| Linux | ssh, scp, rsh |

---

### ✅ Checklist
1. Identify reachable targets (`ping`, `nmap ‑p 22,135,445,3389`).  
2. Validate credential access.  
3. Try RDP or WMIC connection.  
4. Confirm privilege on remote system.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Sysmon 3 / 10 | New network connection by admin tools |
| Security 4624 | Logon Type 3 (lateral) success |
| Sigma | `remote_service_exec.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

