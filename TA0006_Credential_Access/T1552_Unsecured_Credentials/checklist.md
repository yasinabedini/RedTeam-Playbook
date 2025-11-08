# T1552 – Unsecured Credentials

## 🎯 Objective
Locate plaintext or weakly‑hashed credentials from configuration files, scripts, or registry.

---

### 🧰 Tools
findstr /s /i "password=" *.config  
grep ‑r –i "pwd=" /etc/*  
LaZagne – extract local app passwords  

---

### ✅ Checklist
1. Search for plaintext creds in configs (`web.config`, `.env`, `.ini`).  
2. Examine registry for stored RDP / autologon keys.  
3. Harvest from browsers: `Chrome Login Data` DB.  
4. Test decrypted results.

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Sysmon | file read on sensitive paths (`AppData\Roaming\Microsoft\Credentials`) |
| Sigma | `cleartext_creds_access.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

