# T1569 – Service Execution

## 🎯 Objective
Execute code through legitimate service control mechanisms (Windows: sc.exe; Linux: systemd).

---

## 🧰 Tools
| Platform | Tool | Use |
|-----------|------|-----|
| Windows | `sc.exe`, `InstallUtil.exe`, `net start` | execute payload as service |
| Linux | `systemctl`, `service`, `init.d` | run malicious binary as daemon |

---

## ✅ Checklist
1. Create service (`sc create Cleanup binPath= ...`)
2. Start service (`sc start Cleanup`)
3. Confirm process (`tasklist /svc`)
4. Delete service after testing

---

## ⚕ Detection
| Source | Indicator | Rule |
|---------|-----------|------|
| Windows Security | Event 7045 | Service creation |
| Sysmon | ID 1 + parent sc.exe | Suspicious service |
| Linux | /var/log/syslog entries | new service install |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

