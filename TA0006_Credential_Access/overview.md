# TA0006 – Credential Access

> **Goal:** Capture valid authentication material such as hashes, keys, or Kerberos tickets to impersonate legitimate users or elevate privileges within Windows/Linux environments.

---

### ✴ Core Methods
| Technique ID | Technique | Platform | Tools |
|---------------|------------|-----------|--------|
| T1003 | OS Credential Dumping | Win / Lin | Mimikatz, lsassy, secretsdump.py |
| T1552 | Unsecured Credentials | All | findstr, grep, LaZagne |
| T1555 | Password Stores | Win / Lin | DPAPI, browser dump, KeePass viewers |
| T1110 | Brute Force | All | Hydra, CrackMapExec, Kerbrute |
| T1040 | Network Sniffing | All | Wireshark, tcpdump, mitm6 |
| T1558 | Steal or Forge Kerberos Tickets | Win / AD | Rubeus, Impacket, kekeo |

---

### 🔐 Operator Recommendations
- **Never dump LSASS before sandboxing.** Use safe remote extraction (`procdump` / `lsassy`).  
- Extract **NTDS.dat + SYSTEM** for offline cracking.  
- Prefer **Kerberos TGT/TGS ticket theft** over raw lsass if stealth needed.  
- Store credentials in encrypted container (Veracrypt, dtype-safe folder).

---

### 🩸 Blue Team Detection & Hunt
- Sysmon 10/11 (process access to lsass.exe / MiniDumpWriteDump usage).  
- Event ID 4624/4625 + negative cache = brute‑force attempts.  
- Network flow anomalies / sniffing (pcap capture processes).


Author : yasinabedini
GitHub : https://github.com/yasinabedini

