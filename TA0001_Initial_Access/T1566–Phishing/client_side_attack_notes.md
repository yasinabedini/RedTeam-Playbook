# Client‑Side Attack Notes (TA0001.T1566)

## 💡 Summary
Client‑side attacks rely on **user interaction** to execute content delivered by the Red Team.
These include malicious documents, HTML smuggling, ISO/LNK chains, and drive‑by browser exploitation.

---

## 🧬 Technique Breakdown
| Vector | Description | ATT&CK Mapping |
|--------|--------------|----------------|
| Malicious Office Macro | VBA payloads bypassing AMSI / ASR rules | T1204.002 |
| HTML Smuggling | Delivers JS‑built blob object payloads via browser cache | T1566.002 |
| ISO + LNK Chains | Defense evasion for Mark‑of‑the‑Web (MOTW) | T1204.002 + T1059 |
| Drive‑by Compromise | Browser exploitation or plugin‑abuse | T1189 |

---

## 🧰 Useful Labs
- `MATACO.LOCAL\ClientSimulationLab`
- `invoke‑smuggle.ps1` test harness
- `Browser‑Exploit‑Kit (Offline)` for controlled assessment

---

**Detection Tip:**  
Correlate **Outlook process spawn** → `winword.exe` → `shellchild` chain using Sysmon 1 + Parent Hashes.


Author : yasinabedini
GitHub : https://github.com/yasinabedini

