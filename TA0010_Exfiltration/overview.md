# TA0010 – Exfiltration

> **Objective:** Exfiltrate gathered data from the victim environment to an attacker‑controlled system without triggering DLP or network controls.

---

### ⛓ Common Techniques
| ID | Technique | Description | Platform |
|----|------------|--------------|-----------|
| T1041 | Exfiltration Over C2 Channel | Use existing C2 tunnel to send data | All |
| T1048 | Exfiltration Over Alternative Protocol | FTP, SMB, SMTP, ICMP‑based | All |
| T1048.002 | Exfiltration Over HTTPS | Blend in with legitimate HTTPS traffic | All |
| T1567 | Exfiltration to Cloud Storage | Use Dropbox, GDrive, S3, OneDrive | Win / Lin / Cloud |
| T1020 | Automated Exfiltration | Scheduled scripts or agents | All |
| T1011 | Exfiltration Over Other Network Medium | DNS, Bluetooth, Email Tunneling etc. | Win / Lin |
| T1040 | Exfiltration Over Physical Media | USB Drive Copy Out | Win |

---

### ⚙️ Operator Goals
- Move data covertly using **existing channels** or **encrypted HTTPS/DNS tunnels**.  
- Evade **Firewall Egress filtering / DLP rules**.  
- Maintain **consistency of data volume** (chunk and delay).  

---

### 💡 Stealth Guidelines
- Use `certutil.exe -encode` or `base64 | split -b 512k` before sending.  
- Compress archives (7z ‑mx9 ‑p <key>) and rename with benign extension.  
- Schedule low‑bandwidth transfers via PowerShell `Invoke‑WebRequest ‑InFile`.  
- Adjust user agents & inter‑packet timing for normal usage appearance.


Author : yasinabedini
GitHub : https://github.com/yasinabedini

