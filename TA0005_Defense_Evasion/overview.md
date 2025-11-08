# TA0005 – Defense Evasion
> **Purpose:** Conceal activity, disable security mechanisms, and blend into normal system behavior to prevent detection by defenders.

---

### Common Goals
- Obfuscate code, scripts, and payloads (AMSI, AV bypass)
- Disable or tamper with logging and monitoring
- Remove artifacts after execution
- Masquerade under legitimate binaries or processes
- Modify file permissions, timestamps, or metadata
- Hide persistence mechanisms for stealth longevity

---

### High‑Value Windows & Linux Techniques
| Technique | Description | Platform | Typical Tools |
|------------|--------------|-----------|----------------|
| T1036 | Masquerading | Win / Lin | rename binaries, LOLBAS abuse |
| T1562 | Impair Defenses | Win / Lin | tamper EDR, disable logging |
| T1027 | Obfuscate Files/Info | All | Base64, Gzip, Compress payloads |
| T1070 | Indicator Removal | All | clear logs, timestomp, rm –rf |
| T1222 | File Permissions | Lin / Win | icacls, chmod, chown |
| T1564 | Hide Artifacts | Win / Lin | Alternate Data Streams, hidden dirs |



Author : yasinabedini
GitHub : https://github.com/yasinabedini

