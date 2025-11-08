# T1134 – Access Token Manipulation

## 🎯 Objective
Hijack or impersonate access tokens to escalate privileges or move laterally.

---

### 🧰 Tools
- Incognito (CS built‑in)
- Mimikatz: `token::elevate / impersonate`
- Rubeus: `ptt / asktgt`
- PowerShell: `New‑PSSession ‑Configuration TrustedInstaller`

---

### ✅ Checklist
1. Enumerate tokens: `token::list`
2. Impersonate higher token (Administrator / SYSTEM / TrustedInstaller)
3. Execute payload in new context (`runas /user:NT AUTHORITY\SYSTEM cmd`)
4. Cleanup token handles

---

### ⚕ Detection
| Source | Event ID | Indicator |
|---------|-----------|-----------|
| Windows Security | 4624 (Type 3) w/ unusual SID | impersonation |
| Sysmon | 1 + parent=cmd.exe / medium integrity | |
| Sigma | `token_impersonation.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

