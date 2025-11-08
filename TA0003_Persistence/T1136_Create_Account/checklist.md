# T1136 – Create Account

## 🎯 Objective
Establish new local or domain accounts to maintain persistence with valid credentials.

---

### 🧰 Tools / Commands
| Context | Example |
|----------|----------|
| Windows local | `net user backupadmin P@ssword! /add` + `net localgroup administrators backupadmin /add` |
| AD | `dsadd user "CN=svc-updater,CN=Users,DC=corp,DC=local"` |
| Linux | `useradd -m -s /bin/bash support` + `passwd support` |

---

### ⚕ Detection
| Log Source | Event ID | Indicator |
|-------------|-----------|-----------|
| Windows Security | 4720 | User account created |
| Domain Controller | 4728, 4732 | Group membership changes |
| Linux | `/var/log/secure`, `/etc/passwd` diff |
| Sigma | `account_creation.yml`, `sudoers_modification.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

