# T1482 – Domain Trust Discovery (Active Directory)

## 🎯 Objective
Identify domain‑to‑domain trust relationships and paths for lateral movement.

---

### 🧰 Tools
PowerView (`Get-DomainTrust`, `Get-ForestTrust`), BloodHound, ADExplorer, LDAP queries.  

---

### ✅ Checklist
1. Run PowerView trust enumeration.  
2. Identify external and forest trusts.  
3. Map One‑Way vs Two‑Way trusts.  
4. Store results for lateral path generation (BloodHound JSON).  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| LDAP logs | abnormal queries to `trustedDomain` objects |
| Sigma | `domain_trust_enumeration.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

