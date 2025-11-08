# T1557 – Man‑in‑the‑Middle

## 🎯 Objective
Intercept, alter, or redirect network communications for credential capture or session hijack.

---

### 🧰 Tools
Responder, mitm6, Bettercap, NTLMRelayX, Ettercap.  

---

### ✅ Checklist
1. Run LLMNR/NBNS spoof (`responder ‑I eth0 ‑rdw`).  
2. Capture hashes.  
3. Relay to SMB targets (`ntlmrelayx.py ‑smb2support`).  
4. Clean captured hash artifacts.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Zeek | LLMNR/NBT‑NS poison events |
| Sysmon 3 | Unexpected SMB traffic |
| Sigma | `mitm6_detect.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

