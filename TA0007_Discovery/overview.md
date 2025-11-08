# TA0007 – Discovery

> **Goal:** Map out the target environment: users, hosts, domains, trust relationships, systems, and services.

---

### 🔎 Typical Sub‑Tactics
| Technique | Description | Platform | Common Tools |
|------------|-------------|-----------|---------------|
| T1087 | Account Discovery | Win / Lin / AD | net user, dsquery, whoami, Get‑ADUser |
| T1082 | System Information Discovery | Win / Lin | systeminfo, uname ‑a |
| T1016 | Network Configuration Discovery | Win / Lin | ipconfig, ifconfig, netstat |
| T1049 | Network Connections Discovery | Win / Lin | netstat, PowerView |
| T1046 | Network Service Scanning | Win / Lin | nmap, PowerShell Test‑NetConnection |
| T1069 | Permission Groups Discovery | Win / AD | net localgroup, Get‑ADGroupMember |
| T1083 | File and Directory Discovery | All | dir /s, find /etc/passwd, PowerView  |
| T1482 | Domain Trust Discovery | Win / AD | PowerView ‑Get‑DomainTrust, ADExplorer |

---

### 🧰 Operato Insights
- Always log enumeration into a **local artifact container**, never stdout on C2.  
- Chain recon commands into PowerShell modules (`Recon.ps1`) or Python scripts to reduce noise.  
- Prefer **WMI queries** and **LDAP** over direct command‑line enumeration for stealth


Author : yasinabedini
GitHub : https://github.com/yasinabedini

