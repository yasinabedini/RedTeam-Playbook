# T1550 – Use of Authentication Tokens / Kerberos Tickets

## 🎯 Objective
Re‑use stolen tokens (TGT/TGS, JWT, OAuth) to authenticate as legitimate users.

---

### 🧰 Examples
| Token Type | Tools |
|-------------|-------|
| Kerberos TGT/TGS | Rubeus, mimikatz |
| JWT/OAuth | jwt_tool.py, Burp Suite, impacket‑ticketconverter |

---

### ✅ Checklist
1. Collect tokens from memory or cache.  
2. Inject into current session (`Rubeus ptt /ticket:ticket.kirbi`).  
3. Validate access (`dir \\target\C$`).  
4. Rotate tokens to avoid expiration.  

---

### ⚕ Detection
| Source | Indicator |
|---------|------------|
| 4768 / 4769 | abnormal ticket reuse |
| Web app logs | repeated JWT use outside TTL |
| Sigma | `token_reuse_abuse.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

