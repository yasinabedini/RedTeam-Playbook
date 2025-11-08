# T1558 – Steal or Forge Kerberos Tickets

## 🎯 Objective
Steal or maliciously create Kerberos TGT/TGS tickets to impersonate accounts and move laterally.

---

### 🧰 Tools / Commands
| Tool | Usage |
|-------|--------|
| Rubeus | dump tickets (`Rubeus dump`), AS‑REP roast, golden/silver tickets |
| Mimikatz | `kerberos::ptt`, `kerberos::golden` |
| Impacket | `getTGT.py`, `tgtdelegation.py` |

---

### ✅ Checklist
1. Extract krbtgt hash from ntds.  
2. Create golden ticket (mimikatz command).  
3. Inject ticket into session.  
4. Validate access (dir \\DC\C$).

---

### ⚕ Detection
| Source | ID / Signature |
|---------|----------------|
| Windows | 4768 + unusual encryption types |
| Sigma | `kerberos_ticket_anomaly.yml` |
| Zeek | `kerberos_anomalous_tgt` |
1~



# T1558 – Steal or Forge Kerberos Tickets

## 🎯 Objective
Steal or maliciously create Kerberos TGT/TGS tickets to impersonate accounts and move laterally.

---

### 🧰 Tools / Commands
| Tool | Usage |
|-------|--------|
| Rubeus | dump tickets (`Rubeus dump`), AS‑REP roast, golden/silver tickets |
| Mimikatz | `kerberos::ptt`, `kerberos::golden` |
| Impacket | `getTGT.py`, `tgtdelegation.py` |

---

### ✅ Checklist
1. Extract krbtgt hash from ntds.  
2. Create golden ticket (mimikatz command).  
3. Inject ticket into session.  
4. Validate access (dir \\DC\C$).

---

### ⚕ Detection
| Source | ID / Signature |
|---------|----------------|
| Windows | 4768 + unusual encryption types |
| Sigma | `kerberos_ticket_anomaly.yml` |
| Zeek | `kerberos_anomalous_tgt` |



Author : yasinabedini
GitHub : https://github.com/yasinabedini

