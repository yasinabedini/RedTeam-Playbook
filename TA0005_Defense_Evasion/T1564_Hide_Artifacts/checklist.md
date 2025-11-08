# T1564 – Hide Artifacts

## 🎯 Objective
Conceal tools, payloads, or files from defenders and automated scanners.

---

### 🧰 Tools
| Platform | Methods |
|-----------|----------|
| Windows | NTFS Alternate Data Streams, hidden attributes, mountpoints |
| Linux | dot‑files, /proc abuse, LD_PRELOAD cloaking, fusermount |
| Sysadmins | rename within %ProgramData%, symbolic links |

---

### ✅ Checklist
| Step | Action | Example |
|------|---------|----------|
| 1 | Move payload to ADS | `type a.exe > b.txt:secret` |
| 2 | Hide folder | `attrib +h payloads` |
| 3 | Conceal process | inject into legit PID |
| 4 | Linux fusermount redir | mount /tmp as user dir |

---

### ⚕ Detection
| Source | Indicator |
|---------|------------|
| Sysmon | File create → ADS stream |
| Sigma | `ads_creation_detect.yml` |
| Linux | `auditd – hidden_attr` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

