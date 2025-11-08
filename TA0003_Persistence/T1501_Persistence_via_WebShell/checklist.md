# T1501 – Web Shell Persistence (Generic)

## 🎯 Objective
Maintain access through malicious web shell planted on compromised server.

---

### 🧰 Tools
| Stack | Example |
|--------|----------|
| IIS | cmd.aspx / reverse.aspx |
| Apache / nginx | php pentest.php |
| ASPX autoencoder | Encoded C2 gateway |
| Tools: Chisel, reGeorg, China Chopper |

---

### ✅ Checklist
1. Upload shell (`/inetpub/wwwroot/`)
2. Test connectivity
3. Wrap with HTTP header control to evade log signatures
4. Encode and move to alternate directory
5. Cleanup timestamps (T1070.006)

---

### ⚕ Detection
| Source | Indicator |
|---------|------------|
| IIS Log | suspicious querystrings |
| WAF | long base64 payloads |
| EDR | cmd.exe child of w3wp.exe |
| Sigma | `iis_webshell_pattern.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

