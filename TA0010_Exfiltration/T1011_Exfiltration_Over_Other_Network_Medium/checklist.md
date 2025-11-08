# T1011 – Exfiltration Over Other Network Medium

## 🎯 Objective
Use non‑standard network mediums (DNS, Bluetooth, email tunneling) to leak data.

---

### 🧰 Tools
dnscat2, iodine, PowerDNS tunnel, BlueDucky.  

---

### ✅ Checklist
1. Encode data into DNS queries (`base32` chunks).  
2. Configure authoritative domain to receive queries.  
3. Aggregate decoded payload on server.  
4. Purge resolver cache.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| DNS Logs | domains with long subdomain labels > 50 chars |
| Zeek dns.log | high query rate TXT types |
| Sigma | `dns_exfiltration.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

