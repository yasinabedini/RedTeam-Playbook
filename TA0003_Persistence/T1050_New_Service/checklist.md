# T1050 – New Service

## 🎯 Objective
Maintain persistence by registering executables or payloads as system services.

---

### 🧰 Tools
| OS | Tools/Commands |
|----|----------------|
| Windows | sc.exe, PowerShell New‑Service, reg.exe, InstallUtil.exe |
| Linux | systemd, init.d, update‑rc.d, service |

---

### ✅ Operator Checklist
1. Create service with desired binPath:
   - `sc create Updater binPath= "C:\Windows\temp\beacon.exe"`
2. Configure start mode:
   - `sc config Updater start= auto`
3. Start service:
   - `net start Updater`
4. Observe logs (`eventvwr.msc → System` 7045)
5. Remove service post‑operation.

---

### ⚕ Detection
| Source | Event ID | Indicator |
|---------|-----------|-----------|
| Windows Security | 7045 | Service creation |
| Sysmon | 1, 13 | process = sc.exe, reg modifications |
| Linux | journald | new systemd unit file |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

