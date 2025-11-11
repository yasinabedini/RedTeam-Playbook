# T1078 – Valid Accounts
> Exploiting legitimate credentials to access and persist within target environments.

---

## 🎯 Objectives
Leverage valid user, admin, or service accounts—obtained from open‑source breaches or internal harvesting—to gain initial or persistent access without raising authentication alerts.  

---

## 🧰 Tools & Lookup Sources

| Category | Platform | Use‑Case |
|-----------|-----------|----------|
| **Credential Leak Search** | [**LeakCheck.io**](https://leakcheck.io/dashboard) | Search for leaked corporate emails in multiple breach sets |
| | [**DeHashed**](https://dehashed.com) | Cross‑correlation of username / hash / IP / domain records |
| | [**Have I Been Pwned**](https://haveibeenpwned.com) | Public breach notification and verified exposure queries |
| | [**Breach Directory**](https://breachdirectory.org/) | Plaintext / partial hash lookup |
| | [**SOCRadar**](https://socradar.io/thank-you/) | DarkWeb monitoring + credential leak alerts for organizations |
| **Privileged Access Tools** | **Rubeus**, **Mimikatz**, **Impacket** | Token theft / Kerberos abuse after account validation |
| **Automation** | **CME (CrackMapExec)**, **Kerbrute** | Bulk credential validation and domain user brute |

---

## ✅ Operator Checklist

| Step | Task | Example | Done |
|------|------|----------|------|
| 1 | Enumerate org usernames from LinkedIn / AD dump | `firstname.lastname@corp.local` | ☐ |
| 2 | Query breach lookup APIs (LeakCheck / DeHashed) | see if corp email appears in data leak | ☐ |
| 3 | Validate credentials against VPN / OWA / SMB | `crackmapexec smb <target> -u users.txt -p pass.txt` | ☐ |
| 4 | Escalate privilege post‑auth | Kerberos delegation / DCSync / RDP | ☐ |
| 5 | Establish C2 or persistence via scheduled task as valid user | `taskschd.msc > Create Task (run as domain user)` | ☐ |

---

## 🧠 Common Evasion Techniques
- Blend logons with legitimate working hours (using scripted delays).  
- Use VPN/Proxy exit nodes geolocated near target’s region.  
- Rotate credentials across services to reduce failed‑auth patterns.  
- Leverage unmonitored protocols (LDAP/SVN/SharePoint access).  

---

## ⚕ Detection Methods

| Source | Event / Indicator | Detection Tool / Rule |
|---------|------------------|-----------------------|
| **Windows Security** | 4624 Type 3 (logon from unusual host/IP) | Sigma :`susp_logon_unfamiliar_host.yml` |
| **AD Audit** | Multiple user logons from rare subnets | Zeek + Domain Controller Event Correlator |
| **Sysmon** | New network connection followed by token stealing process | `sysmon_evt3_10.yml` |
| **SIEM** | Authentication success after multiple failures (Brute‑then‑Use) | Elastic Rule `auth_success_after_bruteforce` |

---

## 🧾 References
- MITRE ATT&CK: [T1078 – Valid Accounts](https://attack.mitre.org/techniques/T1078/)  
- Red Canary Detection Series #12: Account Abuse  
- SOCRadar Leak Intelligence Portal  
- LeakCheck API Documentation  

---

Author : **yasinabedini**  
GitHub : [https://github.com/yasinabedini](https://github.com/yasinabedini)
