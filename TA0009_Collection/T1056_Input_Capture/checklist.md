# T1056 – Input Capture

## 🎯 Objective
Capture keystrokes, clipboard data, or GUI inputs.

---

### 🧰 Tools
Keysharp, Invoke‑Keylogger, Cobalt Strike Keylogger, xinput hook (Linux).  

---

### ✅ Checklist
1. Inject low‑level keyboard hooks.  
2. Capture input and timestamp.  
3. Exfil secure log to staging folder.  
4. Stop logging after credential capture.  

---

### ⚕ Detection
| Source | Event |
|---------|-------|
| Sysmon 7 | Keyboard API callbacks set by new process |
| Sigma | `keylogger_behavior.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

