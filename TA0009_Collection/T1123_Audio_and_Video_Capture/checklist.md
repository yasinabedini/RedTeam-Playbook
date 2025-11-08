# T1123 – Audio and Video Capture

## 🎯 Objective
Enable microphone or camera recording for credential or visual intel capture.

---

### 🧰 Tools
| Option | Tool |
|--------|------|
| Win | SoundRecorder.exe, DirectShow DLL, screenrecord.ps1 |
| Cross | OBS CLI, ffmpeg |

---

### ✅ Checklist
1. Enumerate devices (`wmic sounddev`, `ffmpeg ‑list_devices`).  
2. Start record with timestamp log.  
3. Limit duration and size.  
4. Encrypt captures (7z ‑p).  

---

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Sysmon 1 / Microsoft Camera Logs | Unexpected recording process |
| Sigma | `video_audio_capture.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

