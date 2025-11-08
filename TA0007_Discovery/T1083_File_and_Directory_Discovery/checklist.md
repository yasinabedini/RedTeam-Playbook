# T1083 – File and Directory Discovery

Identify files and directories of interest for future staging or data theft.

---

### 🧰 Commands
`dir /s /b *.docx`, `find / -type f -name '*.pem'`, `ls -la /home/*/.ssh`

---

### ✅ Checklist
1. Locate credentials, configs, DB files.  
2. Identify file shares (`net view`, `net use`).  
3. Enumerate sensitive drives (`C$, Admin$`).  
4. List mounted storage / NFS points.

---

### ⚕ Detection
| Source | Example Indicator |
|---------|-------------------|
| Sysmon 11 | massive file‑listing loops |
| Sigma | `file_enumeration_spike.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

