# T1547 – Boot or Logon Autostart Execution

## 🎯 Objective
Ensure execution at system boot or user logon via registry keys, startup folders, or logon scripts.

---

### 🧰 Tools
- reg.exe / PowerShell
- persistence.ps1 modules (CS, Sliver)
- WMI subscription with event triggers
- Linux: `.bashrc`, `/etc/profile`, `systemd --user`

---

### ✅ Operator Checklist
| Step | Action | Example |
|------|---------|----------|
| 1 | Registry Run Key | `reg add HKCU\Software\Microsoft\Windows\CurrentVersion\Run /v Updater /t REG_SZ /d beacon.exe` |
| 2 | WMI Event Subscription | `powershell Invoke-WmiMethod` |
| 3 | Linux BashRC Injection | `echo '/opt/payload &' >> ~/.bashrc` |
| 4 | Logon Script Group Policy | `gpmc.msc` |

---

### ⚕ Detection
| Source | Event ID / Rule | Description |
|---------|-----------------|-------------|
| Sysmon | 13, 1 | Registry write Run/RunOnce |
| Sigma | `persistence_registry_run.yml` |
| Linux | Auditd on `.bashrc` modification |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

