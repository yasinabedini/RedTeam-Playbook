# T1563 – Remote Service Session Hijacking

## 🎯 Objective
Hijack legitimate remote user sessions (RDP or service) to avoid authentication.

### 🧰 Techniques
- RDP Shadowing: `mstsc /admin`, `tscon <id> /connect`.  
- Token duplication via `mimikatz token::elevate`.  
- Session swap via `tscon <_targetID_> /session:<current>`.

---

### ✅ Checklist
1. Query sessions: `qwinsta /server:<target>`.  
2. Switch to active session.  
3. Maintain persistence (MSTSC).  
4. Avoid user disruption.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Event 4778 / 4779 | RDP session reconnect |
| Sysmon 1 | tscon.exe spawn |
| Sigma | `rdp_hijack.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

