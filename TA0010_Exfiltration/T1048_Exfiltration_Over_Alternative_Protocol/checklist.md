# T1048 – Exfiltration Over Alternative Protocol

## 🎯 Objective
Send data using external protocols that rarely get egress‑filtered.

### 🧰 Channels
FTP (21), SMTP (25/587), SMB (445), ICMP Echo data fields.

---

### ✅ Checklist
1. Identify open egress ports.  
2. Encode payload (Base64).  
3. Send via alternative client (e.g., `curl ‑T data ftp://...`).  
4. Verify round‑trip latency & integrity.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Zeek conn.log | unusual FTP uploads |
| Sysmon 3 | outbound ICMP > 500 bytes steady pattern |
| Sigma | `exfil_over_alt_protocol.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

