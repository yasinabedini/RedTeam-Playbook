# T1087 – Account Discovery

## 🎯 Objective
Enumerate user and group accounts across local and domain contexts.

---

### 🧰 Tools / Commands
| Platform | Commands |
|-----------|-----------|
| Windows | `net user /domain`, `Get-ADUser -Filter *`, `whoami /all` |
| Linux | `cat /etc/passwd`, `id`, `ldapsearch` if domain-linked |

---

### ✅ Checklist
1. Enumerate local users (`net user`).  
2. Domain accounts enumeration (`Get-ADUser`, `dsquery user`).  
3. Identify admin groups (`net localgroup administrators`).  
4. Search for exposed service accounts.  
5. Record and map user–host relations.

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Security Log 4720 | New user enumerated |
| Sysmon 1 | Suspicious net commands |
| Sigma | `account_enumeration.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

