# T1110 – Brute Force

## 🎯 Objective
Guess passwords via repeated authentication attempts (local, network, cloud).

---

### 🧰 Tools
Hydra / Medusa / CrackMapExec / Kerbrute / Patator  

---

### ✅ Checklist
1. Identify service/auth target (RDP, SMB, SSH, Kerberos).  
2. Test credentials safely (`--rate-limit`).  
3. Capture successful tokens or hashes.  
4. Evade alert thresholds (use slow bruting).

---

### ⚕ Detection
| Event | Indicator |
|--------|------------|
| 4625 (Win) / auth.log (Lin) | many failed logins same src IP |
| Sigma | `brute_force_multiple_failures.yml` |
| Zeek | `ssh_auth_fail` pattern |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

