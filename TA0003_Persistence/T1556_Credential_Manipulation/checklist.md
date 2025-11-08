# T1556 – Credential Manipulation

## 🎯 Objective
Modify authentication mechanisms or stored credentials to maintain stealthy access.

---

### 🧰 Tools
- Mimikatz, SafetyKatz
- Rubeus (for ticket patching)
- Keychain injection / PAM module abuse

---

### ✅ Checklist
| Task | Example |
|------|----------|
| Patch LSASS | `mimikatz privilege::debug sekurlsa::pth /user:svc /rc4:...` |
| Create rogue Kerberos ticket | `rubeus asktgt /user:svc /rc4:hash` |
| Linux PAM abuse | replace `/etc/pam.d/su` with backdoor module |

---

### ⚕ Detection
| Source | Indicator |
|---------|------------|
| Windows | EID 4624 anomalies with non‑existent user | 
| Sysmon | LSASS read + mem modifications |
| Sigma | `credential_theft_mimikatz.yml`, `tampered_pam.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

