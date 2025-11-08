# T1133 – External Remote Services

## 🧰 Tools
| Tool | Use |
|------|-----|
| `rdpscan`, `crowbar` | check RDP/VPN credentials |
| `CrackMapExec`, `Evil‑WinRM` | auth+exec |
| `SSHuttle`, `Chisel`, `Sliver SOCKS` | pivoting |
| `openvpn3`, `forticlient‑ssl‑vpn` | VPN tunnel |

---

## ✅ Checklist
1. Gather leaked creds / Spray.  
2. Enumerate exposed RDP/VPN/SSH endpoints.  
3. Attempt access (non‑destructive proof).  
4. Drop In‑Memory Agent if permitted.  

---

## ⚕ Detection
- Windows EVT 4625 (RDP failed login), 4624 (success type 10).  
- GeoIP anomaly (ASNs from non‑business countries).  
- VPN portal multiple auth attempts.  
- SIGMA: `rdp_bruteforce.yml`, `vpn_anomaly.yml`.


Author : yasinabedini
GitHub : https://github.com/yasinabedini

