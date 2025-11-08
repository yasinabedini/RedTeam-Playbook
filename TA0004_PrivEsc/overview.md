# TA0004 — Privilege Escalation

> **Goal:** Obtain elevated privileges to control systems or domains beyond initial access.

---

### 🔑 Common Paths
| Technique ID | Description | Platform | Common Tools |
|---------------|--------------|-----------|---------------|
| T1068 | Exploitation for Privilege Escalation | Win / Lin | JuicyPotato, DirtyPipe, CVE kits |
| T1055 | Process Injection | Win | Cobalt Strike BOFs, Donut, SharpInjector |
| T1078 | Valid Accounts (Priv) | Win / Lin / AD | Rubeus, Mimikatz, sudo abuse |
| T1134 | Access Token Manipulation | Win | Incognito, PS token tools |
| T1548 | Abuse Elevation Control (UAC/Sudo) | Win / Lin | UACME, RunAs, sudo misconfig |
| T1611 | Sudo & SUID Abuse | Linux | find ‑perm ‑4000, GTFOBins |
| T1547 | Boot/Logon Autostart Elevated | Win / Lin | Reg keys, systemd root start |

---

### 🧭 Operator Hints
- Always **enumerate first** (`whoami /priv`, `groups`, `sudo ‑l`, `accesschk.exe`).
- Go for **“noisy but one‑shot”** exploits only when other persistence is ready.
- Map EDR/AMSI coverage before payload injection in elevated context.


Author : yasinabedini
GitHub : https://github.com/yasinabedini

