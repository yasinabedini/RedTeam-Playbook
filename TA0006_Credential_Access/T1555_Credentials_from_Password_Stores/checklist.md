# T1555 – Credentials from Password Stores

## 🎯 Objective
Extract saved passwords from applications (browsers, credential vaults, DPAPI).

---

### 🧰 Tools
| Environment | Example |
|--------------|----------|
| Windows | DPAPI extract, mimikatz (`dpapi::cred`) |
| Linux | seahorse, gnome‑keyring‑dump |
| Cross  | LaZagne, browserdump.py |

---

### ✅ Checklist
1. Enumerate credential stores.  
2. Extract DPAPI master key.  
3. Decrypt stored blobs (mimikatz `/in:path /masterkey:`).  
4. Dump browser SQLite DB: `SELECT origin_url, username, password_value`.

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Windows Event | 4662 + `Credential Manager` access |
| Sigma | `dpapi_dump_detect.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

