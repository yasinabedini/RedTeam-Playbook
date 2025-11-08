# T1040 – Exfiltration Over Physical Media

## 🎯 Objective
Transfer data using removable drives or external hardware.

---

### 🧰 Tools
cmd, PowerShell Copy‑Item, rsync usb mount.  

---

### ✅ Checklist
1. Plug encrypted USB (Storage Vault).  
2. Copy target archives (`robocopy D:\stage E:\ /s`).  
3. Hash files post‑copy.  
4. Physically remove device and wipe MFT.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Sysmon 1 / USB Events | new removable drive mount |
| Audit 4663 | large copy operations |
| Sigma | `physical_exfil.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

