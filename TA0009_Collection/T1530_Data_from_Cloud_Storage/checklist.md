# T1530 – Data from Cloud Storage

## 🎯 Objective
Access or export sensitive files from cloud storage services.

---

### 🧰 Examples
OneDrive Client, rclone, gsutil, AWS CLI, azcopy.  

---

### ✅ Checklist
1. Verify cloud sync paths.  
2. Estimate available API tokens.  
3. Use cloud CLI tools for copy.  
4. Encrypt local cache after sync.  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Cloud Audit | API list or download events in bulk |
| Sigma | `cloud_data_export.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

