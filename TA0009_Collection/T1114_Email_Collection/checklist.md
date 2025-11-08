# T1114 – Email Collection

## 🎯 Objective
Collect email content from local clients or mail servers.

---

### 🧰 Tools
| Target | Tools |
|---------|-------|
| Outlook/PST | NirSoft MailPassView, PowerShell MAPI |
| Exchange/IMAP | ruler, ewsManage, fetchmail |
| Cloud | MSGraph API, Impacket office365_extract |

---

### ✅ Checklist
1. Locate PST/OST files (`C:\Users\*\AppData\Local\Microsoft\Outlook`).  
2. Dump mailboxes via Outlook COM API or Graph API.  
3. Compress and tag emails.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| 4663 on *.pst | high volume file read |
| O365 Audit | user initiated Export‑Mailbox |
| Sigma | `email_collection_activity.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

