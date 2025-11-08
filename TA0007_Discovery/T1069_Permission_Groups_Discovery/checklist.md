# T1069 – Permission Groups Discovery

## 🎯 Objective
Enumerate system and domain group memberships to identify privileged accounts.

### Commands
`net localgroup`, `Get-ADGroup`, `Get-ADGroupMember -Recursive`.  
Linux: `id`, `groups`, `getent group`.

### ✅ Checklist
1. Enumerate local adminmatic groups.  
2. Identify domain privileged groups.  
3. Map membership using PowerView.  
4. Cross‑correlate with known admins from AD.  

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| 4799 | Enumeration of group membership |
| Sysmon | wmic / net.exe abuse |
| Sigma | `privilege_group_enum.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

