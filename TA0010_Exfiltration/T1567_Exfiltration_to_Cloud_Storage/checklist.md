# T1567 – Exfiltration to Cloud Storage

## 🎯 Objective
Abuse legitimate cloud funnels (Drive, Dropbox, S3, Azure Blob) to smuggle data out.

---

### 🧰 Tools
rclone, aws cli, azcopy, OneDrive Graph API.  

---

### ✅ Checklist
1. Configure temporary token (`aws configure --profile temp`).  
2. Stage files to %TEMP%\stage.  
3. Upload via HTTPS to object store bucket.  
4. Delete token cache and history.  

---

### ⚕ Detection
| Platform | Indicator |
|-----------|-----------|
| Cloud Audit | unusual upload volume from endpoint |
| Sysmon 1 | execution of rclone.exe / aws.exe |
| Sigma | `cloud_exfil.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

