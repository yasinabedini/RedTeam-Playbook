# T1046 – Network Service Scanning

## 🎯 Objective
Identify active hosts and services in target network ranges.

---

### 🧰 Tools
Nmap, Masscan, CrackMapExec, SharpMapExec, ldapsearch.  

---

### ✅ Checklist
1. Define scope (`/24` or subnet list).  
2. Passive first (ARP, NetBIOS).  
3. Active scan when permitted (`nmap -sS -p 445,3389`).  
4. Identify domain controllers / file shares.  

---

### ⚕ Detection
| Source | Indicator |
|---------|------------|
| Zeek | portscan.log > threshold |
| Suricata | SCAN 504 alerts |
| Sigma | `nmap_execution.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

