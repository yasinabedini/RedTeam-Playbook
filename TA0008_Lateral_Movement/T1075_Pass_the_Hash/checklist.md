# T1075 – Pass the Hash

## 🎯 Objective
Authenticate without knowing plaintext passwords by reusing NTLM hashes.

---

### 🧰 Tools
Mimikatz (sekurlsa::pth), Impacket psexec.py / wmiexec.py, CrackMapExec.  

---

### ✅ Checklist
1. Obtain NTLM hashes (via lsass dump or SAM).  
2. Execute `mimikatz privilege::debug` + `sekurlsa::pth /user:admin /domain:corp.local /ntlm:<hash>`.  
3. Lateral move to target host.  
4. Clear logs and evidence.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Event 4624 | Logon Type 3 + `NtLmSsp` authentication package |
| Sysmon 1 | Execution of mimikatz /PTH modules |
| Sigma | `pass_the_hash.yml` |



Author : yasinabedini
GitHub : https://github.com/yasinabedini

