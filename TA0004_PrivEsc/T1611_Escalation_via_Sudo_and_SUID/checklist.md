# T1611 – Sudo / SUID Privilege Escalation (Linux)

## 🎯 Objective
Abuse misconfigured SUID binaries or sudo permissions.

---

### ✅ Checklist
1. Enumerate privs:
   - `sudo ‑l`  
   - `find / ‑perm ‑4000 ‑type f 2>/dev/null`
2. Exploit SUID binary (`vim`, `less`, `bash`)
3. Replace wrapper scripts
4. Validate clean exit & restore permissions

---

### 🧰 Tooling
- linpeas.sh / linenum.sh
- GTFOBins
- pspy for process detection

---

### ⚕ Detection
| Source | Rule |
|---------|------|
| Auditd | `execve / usr/bin/sudo` with unexpected TTY |
| Sigma | `sudo_privilege_misuse.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

