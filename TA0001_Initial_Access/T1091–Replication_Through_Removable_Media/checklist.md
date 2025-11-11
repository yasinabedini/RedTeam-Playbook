# T1091 – Replication Through Removable Media

## 🧰 Tools
| Tool | Purpose |
|------|----------|
| `USBStealer`, `Dusty` | Copy to drives w/ autorun |
| `Coercer`, `PSAutorun` | LNK autostart creation |
| `Disable‑MOTW.ps1` | Bypass mark‑of‑web |
| `SharpDriveSpread` | internal lab benchmark |

POC : https://github.com/thehackercat/USBthief
Scan Removable Drivers And copy data from usb to system
---

## ✅ Checklist
1. Build autorun.inf or LNK dropper.  
2. Evade AMSI / defender by archive ISO.  
3. Monitor for execution via Sysmon 6.  
4. Log hostnames infected for chain‑mapping.  

---

## ⚕ Detection
- Device mount → binary execution (Seq: EID 6416 → 1).  
- Unknown LNK shortcut in removable root.  
- Command‑line exec from `E:\`, `F:\`, `G:\` paths.


Author : yasinabedini
GitHub : https://github.com/yasinabedini

