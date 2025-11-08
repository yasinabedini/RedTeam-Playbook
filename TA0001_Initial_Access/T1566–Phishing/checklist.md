# T1566 – Phishing (Attachment / Link)
> Gaining initial foothold through crafted emails or cloud-delivered lures.

---

## 🎯 Objectives
Deliver a weaponized file or URL that, upon user interaction, results in code execution (macro, HTML-smuggled JS, ISO/LNK chain, etc.).

---

## 🧰 Tools & Frameworks
| Category | Tool | Use Case |
|-----------|------|---------|
| Campaign Manager | **GoPhish**, **KingPhisher** | full email lifecycle |
| Payload Builders | **Invoke‑HTMLSmuggle**, **Doughnut**, **SharpShooter** | macro & HTML payloads |
| Command & Control | **Cobalt Strike**, **Sliver**, **Mythic** | staged callback |
| Infra | **CanaryTokens**, **LetsPhish**, **MailFlowLab** | tracking and sandbox evasion |

---

## ✅ Operator Checklist
| Step | Task | Example | Done |
|------|------|----------|------|
| 1 | Build pretext | M365 alert / HR doc message | ☐ |
| 2 | Generate lure PDF/HTML | HTML smuggling with blob payload | ☐ |
| 3 | Setup secure sender infra | `smtp.relay[.]net:587` TLS | ☐ |
| 4 | Send campaign test to safe mailbox | verify delivery / render | ☐ |
| 5 | Deliver to target subset | Monitor inbound beacons | ☐ |

---

## 🧠 Common Evasion Techniques
- Rename `.iso` → legitimate archive signature.
- OneNote embedded LNK payloads.
- Disable MOTW through archive extraction (7‑Zip).

---

## ⚕ Detection Methods
| Source | Event / Indicator | Tool / Rule |
|---------|------------------|-------------|
| **Mail Gateway** | Header anomaly + SPF/DKIM fail | Secure Email Gateway |
| **EDR/AV** | `WINWORD.exe → CMD.EXE → PowerShell` chain | Sysmon EID 1 | 
| **Network** | Outbound HTTPS to uncategorized domain | DNS Logs + Proxy alert |
| **M365** | Suspicious inbox rule / mass read | Microsoft Defender for O365 |
| **Sigma** | `proc_creation_office_spawns_cscript.yml` | SIGMA / Elastic Detection |

---

## 🧾 References
- MITRE T1566 [v15](https://attack.mitre.org/techniques/T1566/)
- SpecterOps – Modern Phishing Chains


Author : yasinabedini
GitHub : https://github.com/yasinabedini

