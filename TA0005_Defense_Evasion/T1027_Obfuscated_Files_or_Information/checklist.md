# T1027 – Obfuscated Files or Information

## 🎯 Objective
Hide payloads or scripts through encryption, compression, or encoding.

---

### 🧰 Tools
- PowerShell Base64, RC4, AES stagers  
- `upx`, `gzinflate`, `Invoke‑Obfuscation`, `Donut`, `pyarmor`  
- Linux: tar + gzip + openssl enc ‑aes256  

---

### ✅ Checklist
| Task | Command |
|------|----------|
| Encode script | `cat payload.ps1 | iconv | base64` |
| Encrypt binary | `openssl aes‑256‑cbc ‑in a.exe ‑out b.enc` |
| Custom loader decode | via CS/Sliver BOF |
| Test AMSI response | check if decode triggers scan |

---

### ⚕ Detection
| Source | Signature |
|---------|------------|
| PowerShell | EncodedCommand usage |
| Sysmon | File creation with `.b64`, `.enc` |
| Sigma | `encoded_command_execution.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

