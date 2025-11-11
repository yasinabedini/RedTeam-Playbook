# T1200 – Hardware Additions

## 🧰 Tools
- **Hak5 Rubber Ducky / Bash Bunny**
- **Flipper Zero HID payloads**
- **Teensy macro injectors**

---

## ✅ Checklist
| Step | Task | Expected Result |
|------|------|----------------|
| 1 | Encode payload (Shellcode / AutoHotKey) | Binary ready for HID |
| 2 | Plant device physically | Device seen in PnP logs |
| 3 | Payload executes | Reverse shell callback |
| 4 | Remove device / cleanup | No residual artifact |

## ⚕ Detection
- Windows Event 6416 (Device Connected).  
- New USB Vendor ID ≠ approved list.  
- Endpoint DLP alerts on drive insert.

---

## 🧾 References
- MITRE ATT&CK: [T1190  –Exploit Public‑Facing Application](https://attack.mitre.org/techniques/T1190/)  

---

Author : yasinabedini
GitHub : https://github.com/yasinabedini

