# T1055 – Process Injection

## 🎯 Objective
Inject malicious code into legitimate processes for privilege gain or evasion.

---

### 🧰 Tools
- Cobalt Strike BOF, SharpInjector, PoshInjection
- Donut/SRDI in‑memory loaders
- PowerSploit – Invoke‑ReflectivePEInjection

---

### ✅ Checklist
1. Identify target process: `explorer.exe`, `winlogon.exe`, `lsass.exe` (read‑only).
2. Perform injection (CreateRemoteThread, APC, Reflective).
3. Verify elevated token.
4. Watch EDR call‑stack; prefer `QueueUserAPC` or `NtMapView`.

---

### ⚕ Detection
| Source | ID / Rule | Note |
|---------|------------|------|
| Sysmon | 8, 7, 10 | process injection, image load anomalies |
| ETW | Event 1000–1006 PowerShell logging | script injection |
| Sigma | `proc_injection_detect.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

