# T1082 – System Information Discovery

## 🎯 Objective
Collect system details such as OS version, architecture, hostname, domain, and installed software.

---

### 🧰 Commands
| Platform | Example |
|-----------|----------|
| Windows | `systeminfo`, `gpresult /r`, `wmic os get Caption,CSDVersion,OSArchitecture` |
| Linux | `uname -a`, `lsb_release -a`, `hostnamectl` |

---

### ✅ Checklist
1. Gather host metadata.  
2. Identify malware sandbox signs (odd CPUs, usernames, ram < 2 GB).  
3. Save OS version for exploit correlation.  
4. Collect AD domain affiliations (`echo %LOGONSERVER%`).  

---

### ⚕ Detection
| Log Source | Indicator |
|-------------|-----------|
| Sysmon 1 | systeminfo.exe execution from non‑admin user |
| Sigma | `system_information_discovery.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

