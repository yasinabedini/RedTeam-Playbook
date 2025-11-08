# TA0008 – Lateral Movement

> **Objective:** Move laterally through networked systems using valid credentials, remote services, or hijacking existing sessions.

---

### ⚙️ Typical Techniques
| ID | Technique | Platform | Common Tools |
|----|------------|-----------|---------------|
| T1021 | Remote Services | Win / Lin | PsExec, wmic, ssh |
| T1075 | Pass the Hash | Win / AD | Mimikatz, Impacket psexec.py |
| T1550 | Use of Web Tokens / Kerberos Ticket | Win / AD | Rubeus, Impacket |
| T1105 | Remote File Copy | All | SMB, SCP, RDP, bitsadmin, certutil |
| T1563 | Remote Service Session Hijacking | Win | RDP hijack, Task Hijack |
| T1557 | Man‑in‑the‑Middle | All | Responder, mitm6, Bettercap |

---

### 🧩 Operator Goals
- Establish **control over multiple hosts**.  
- Maintain **Domain lateral awareness (AD graph)** via BloodHound or PowerView.  
- Move covertly using **valid credentials**; avoid new process creation patterns.  

### 💡 Stealth Guidelines
- Prefer **WMI, PowerShell Remoting, RPC** instead of noisy network tools.
- Use **Kerberos ticket injection (Pass‑the‑Ticket)** rather than raw hash usage.
- Whenever possible, piggyback on **existing RDP sessions or remote services**.


Author : yasinabedini
GitHub : https://github.com/yasinabedini

