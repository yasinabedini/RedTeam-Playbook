# TA0001 – Initial Access
> **Goal:** Gain an initial foothold within the target environment through user interaction, exposed services, or supply-chain abuse.

---

## 🎯 Primary Objectives
- Deliver and execute payloads on target systems.
- Exploit perimeter weaknesses.
- Rely on user‑assisted infection vectors.
- Establish initial command‑and‑control channel.

---

## 🔬 Example Entry Vectors
| ID | Technique | Vector Summary |
|----|------------|----------------|
| T1566 | Phishing | Email‑based delivery via malicious attachments or links |
| T1190 | Exploit Public‑Facing Application | Leverage vulnerable web or network service |
| T1133 | External Remote Services | Use of VPN/RDP/SSH credentials from external network |
| T1200 | Hardware Additions | Implant infected USB devices or peripherals |
| T1091 | Replication through Removable Media | Propagate through USB drives or shared storage |

---

## 🔗 Operational Tips
- Stage payloads through CDN or obfuscated artifact hosting.
- Blend with normal web requests (`User‑Agent`, `TLS SNI` mimicry).
- Leverage HTML smuggling for cloud‑filtered environments.
- Maintain logs for every access vector used during ops.

---

**Tags:** `#TA0001` `#MITREv15` `#InitialAccess`  



Author : yasinabedini
GitHub : https://github.com/yasinabedini

