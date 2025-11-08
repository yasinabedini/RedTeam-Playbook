# T1048.002 – Exfiltration Over HTTPS

## 🎯 Objective
Blend exfiltration inside typical HTTPS traffic to bypass firewalls.

---

### 🧰 Tools
curl, Invoke‑WebRequest, rclone over HTTPS, Python requests.

---

### ✅ Checklist
1. Split archive into 512 KB chunks.  
2. Encode each part (Base64 UTF‑8).  
3. POST to attacker endpoint (`https://cdn‑like‑domain/upload`).  
4. Randomize User‑Agent & delays.  
5. Rotate domains every N uploads.

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Proxy / Zeek SSL Logs | Outbound large POST traffic to unknown cert CN |
| Sigma | `exfil_over_https.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

