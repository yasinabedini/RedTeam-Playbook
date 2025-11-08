# T1041 – Exfiltration Over Command and Control Channel

## 🎯 Objective
Transfer collected files using an already‑established C2 (HTTP/S, DNS, SMB, TCP).

---

### 🧰 Tools
Cobalt Strike, Sliver, Mythic, Impacket smbexec, custom Python C2.

---

### ✅ Checklist
1. Prepare staging folder (`C:\Users\Public\stage` or `/tmp/stage`).  
2. Compress & encrypt (`7z a ‑tzip data.zip ‑p<key>`).  
3. Use built‑in C2 upload module (`upload data.zip`).  
4. Validate MD5 checksum server‑side.  
5. Clear staging artifacts.

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Zeek & Proxy | POST requests to rare domains w/ large payloads |
| Sysmon 3 / 10 | Outbound connection to non‑business IP on 443 or 8080 |
| Sigma | `exfil_over_c2.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

