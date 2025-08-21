# Windows System Artifacts and Forensic Tools

This repository provides a comprehensive overview of important Windows system files, caches, logs, and artifacts, as well as the tools commonly used to analyze them for forensic investigations, incident response, or system troubleshooting.

---

## 1. Program Compatibility Assistant (PCA)

**File/Location:**  
- `C:\Windows\System32\PcaSvc.dll`  
- `C:\Windows\System32\CompatTelRunner.exe`  
- Event logs: `Applications and Services Logs > Microsoft > Windows > ProgramCompatibilityAssistant`

**Purpose:**  
- Detects compatibility issues for older programs on newer Windows versions.  
- Suggests fixes or runs the program in compatibility mode automatically.  

**Key Points:**  
- Logs application paths, execution status, and timestamps.  
- Useful for determining if an application ran despite warnings.  

---

## 2. Windows Search Index (Windows.edb)

**File/Location:**  
- `C:\ProgramData\Microsoft\Search\Data\Applications\Windows\Windows.edb`

**Purpose:**  
- Stores metadata and indexes of files, emails, and other content for faster search.  

**Key Points:**  
- Can reveal deleted or moved files if the database is not updated.  
- Tools for analysis: **MFTECmd**, **ESENTUTL**, **X-Ways Forensics**.  

---

## 3. Icon Cache Files

**File/Location:**  
- `C:\Users\<username>\AppData\Local\IconCache.db`  
- `C:\Users\<username>\AppData\Local\Microsoft\Windows\Explorer\iconcache_*.db`

**Purpose:**  
- Speeds up loading of folder and program icons.  

**Key Points:**  
- Can reveal deleted applications.  
- Can be rebuilt using `ie4uinit.exe -ClearIconCache`.  

---

## 4. Thumbnail Cache Files

**File/Location:**  
- `C:\Users\<username>\AppData\Local\Microsoft\Windows\Explorer\thumbcache_*.db`

**Purpose:**  
- Stores thumbnails of images, videos, and documents for fast preview in Explorer.  

**Key Points:**  
- Forensic relevance: shows previously viewed images, even if deleted.  
- Different sizes of thumbnails stored in separate files.

---

## 5. Prefetch Files

**File/Location:**  
- `C:\Windows\Prefetch\*.pf`

**Purpose:**  
- Speeds up application startup by caching portions of executable files.  

**Key Points:**  
- Shows the last run time and frequency of execution.  
- Can reveal deleted applications or recently run programs.  

---

## 6. LNK (Shortcut) Files

**File/Location:**  
- Anywhere on the system, commonly `C:\Users\<username>\Desktop`  

**Purpose:**  
- Windows shortcuts pointing to files or folders.  

**Key Points:**  
- Can reveal original file paths and last access times.  
- Useful for tracing deleted files or user activity.  

---

## 7. Master File Table ($MFT)

**File/Location:**  
- `C:\$MFT` (NTFS volume root)

**Purpose:**  
- Central index of all files on NTFS volumes.  

**Key Points:**  
- Includes information about deleted files, sizes, timestamps, and attributes.  

---

## 8. USN Journal

**File/Location:**  
- `C:\$Extend\$UsnJrnl`

**Purpose:**  
- Logs all changes made to files on NTFS volumes.  

**Key Points:**  
- Useful to track file creation, modification, and deletion.  

---

## 9. NTUSER.DAT (User Registry Hive)

**File/Location:**  
- `C:\Users\<username>\NTUSER.DAT`

**Purpose:**  
- Stores user-specific settings, configurations, and MRU (Most Recently Used) lists.  

**Key Points:**  
- Can reveal recently opened files, mounted drives, and USB history.  

---

## 10. Windows Event Logs

**File/Location:**  
- `C:\Windows\System32\winevt\Logs\*.evtx`

**Purpose:**  
- Stores system, application, and security events.  

**Key Points:**  
- Critical for analyzing system behavior, logon activity, and program execution.  

---

## 11. Recycle Bin

**File/Location:**  
- `C:\$Recycle.Bin\<SID>\`

**Purpose:**  
- Stores deleted files until emptied.  

**Key Points:**  
- Can recover deleted files along with deletion timestamps.  

---

## 12. Prefetch and Jumplists

**File/Location:**  
- `C:\Windows\Prefetch\*.pf`  
- `C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations`  
- `C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Recent\CustomDestinations`

**Purpose:**  
- Tracks recently executed programs (Prefetch) and recently accessed files (Jumplists).  

**Key Points:**  
- Provides detailed user activity and timeline reconstruction.

---

## 13. Tools for Analysis

| Tool                         | Purpose                                                                 |
|-------------------------------|-------------------------------------------------------------------------|
| **MFTECmd**                   | Parse Windows.edb and event artifacts                                   |
| **ESENTUTL**                  | Inspect and repair ESE databases like Windows.edb                       |
| **Thumbcache Viewer**         | View contents of thumbnail cache files                                   |
| **FTK Imager**                | Mount and examine disk images                                            |
| **HxD**                       | Hex editor for examining raw file contents                               |
| **Disk Drill / Recuva / WinFR**| Recover deleted files from disks                                         |
| **Arsenal Image Mounter**     | Mount disk images as virtual drives for analysis                         |
| **PowerShell**                | Automate file combining, data extraction, and analysis scripts          |
| **Registry Explorer / RECmd** | Examine Windows registry hives and extract artifacts                    |
| **Autopsy / Sleuth Kit**      | Full-disk forensic analysis, timeline creation, and artifact extraction |
| **LogParser / LogParser Lizard** | Query and analyze event logs, CSVs, and structured text logs          |
| **OSForensics**               | Artifact collection, timeline analysis, and deleted file recovery        |
| **Belkasoft Evidence Center** | Comprehensive DFIR suite for system artifacts analysis                  |
| **Bulk Extractor**            | Extract emails, URLs, credit cards, and other data from raw disk images  |
| **Magnet AXIOM / AXIOM Examine** | Commercial DFIR suite for disk, memory, and cloud artifact analysis    |
| **X-Ways Forensics**          | Low-level disk analysis and data recovery                                 |
| **Volatility / Rekall**       | Memory forensics, RAM dump analysis                                      |
| **FTK Toolkit / EnCase**      | Enterprise forensic suites for disk and artifact analysis               |
| **Mandiant Redline**          | Memory and host-based forensic analysis                                  |

---

## References

- [Program Compatibility Assistant (Microsoft Docs)](https://docs.microsoft.com/en-us/windows/deployment/planning/program-compatibility-assistant)  
- [MFTECmd – Eric Zimmerman](https://ericzimmerman.github.io/)  
- [Magnet AXIOM](https://www.magnetforensics.com/resources/magnet-axiom/)  
- *Windows Internals, 7th Edition* by Mark Russinovich  
- DFIR Tools & Techniques Documentation

