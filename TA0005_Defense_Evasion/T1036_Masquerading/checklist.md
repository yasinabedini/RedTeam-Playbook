# T1036 – Masquerading

## 🎯 Objective
Deceive defenders or security tools by mimicking legitimate names, paths, or binaries.

---

### 🧰 Tools / Techniques
| OS | Examples |
|----|-----------|
| Windows | rename to `svchost.exe`, use signed LOLBAS (msbuild.exe, wmic.exe) |
| Linux | rename `/tmp/bash` to `/usr/sbin/cron` |
| Frameworks | Sliver, CS – “spawnto” parent spoof |

---

### ✅ Checklist
1. Rename payload to trusted binary name.  
2. Placement in system directory to mimic authentic location.  
3. Modify PE metadata (`rcedit`, `sigthief`).  
4. Adjust timestamps (T1070.006).  
5. Execute under trusted process (via process hollowing).

---

### ⚕ Detection
| Source | Rule |
|---------|------|
| Sysmon | ID 1 + Parent Image Mismatch |
| Sigma | `process_image_masquerade.yml` |
| Linux | `auditd -- PATH mismatch` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

