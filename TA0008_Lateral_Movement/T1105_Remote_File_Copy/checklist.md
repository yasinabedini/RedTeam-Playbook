# T1105 – Remote File Copy

## 🎯 Objective
Transfer tools or payloads between systems.

---

### 🧰 Tools / Methods
SMB (copy \\host\C$), SCP, RDP clipboard, bitsadmin.exe, certutil.exe.  

---

### ✅ Checklist
1. Use built‑in tools (certutil /urlcache, bitsadmin).  
2. SCP transfer (if SSH available).  
3. Verify integrity via hash.  
4. Wipe transit copy after execution.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Sysmon 3 | connections to 445 / 139 from unusual user agent |
| Sigma | `remote_file_copy.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

