# T1040 – Network Sniffing

## 🎯 Objective
Capture network traffic to extract credentials in transit.

---

### 🧰 Tools
Wireshark, tcpdump, Responder, mitm6, Bettercap  

---

### ✅ Checklist
1. Setup passive capture (`tcpdump ‑i eth0 port 88 or 389`).  
2. Identify credentials (HTTP Basic, LDAP simple, NTLMv1).  
3. Active poisoning via Responder / mitm6 if allowed.  
4. Export hashes for offline cracking.

---

### ⚕ Detection
| Source | Indicator |
|---------|------------|
| Zeek | `notice.log` – LLMNR/nbns/MDNS poisoning |
| Sysmon | new driver install pcap tools |
| Sigma | `network_sniffer_install.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

