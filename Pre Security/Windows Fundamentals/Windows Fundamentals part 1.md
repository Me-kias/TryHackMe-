# TryHackMe – Windows Fundamentals 1 (Notes)

## Task 1: Remote Desktop (RDP)


## Task 2: Windows Editions
- Windows has many editions (Home, Pro, Enterprise, etc.)
- Different editions have different features
- **BitLocker** is not available on all editions

- Feature missing on some editions: **BitLocker**

---

## Task 3: Windows Desktop (GUI)
Main components:
- Desktop
- Start Menu
- Search Box
- Taskbar
- Notification Area

Key points:
- Right-click taskbar to customize
- You can hide:
  - Search box
  - Task View button

---

## Task 4: Windows File System
- Modern Windows uses **NTFS**
- Older systems used FAT16 / FAT32 / HPFS

### NTFS Features
- File/folder permissions
- Journaling (auto-repair)
- Alternate Data Streams (ADS)

**Permissions include:**
- Full Control
- Modify
- Read & Execute
- Read
- Write

### Alternate Data Streams (ADS)
- Files can contain hidden data
- Often abused to hide malware
- Not visible in File Explorer
- Can be detected via PowerShell

- NTFS stands for **New Technology File System**

---

## Task 5: Windows & System32 Folder
- Windows OS files stored in:
  ```
  C:\Windows
  ```
- Critical system files stored in:
  ```
  C:\Windows\System32
  ```
- Messing with System32 can break Windows

### Environment Variable
- `%windir%` → points to Windows folder

- System variable for Windows folder: `%windir%`

---

## Task 6: User Accounts & Permissions
### Account Types
- **Administrator**: full system control
- **Standard User**: limited access

### Viewing Users
- GUI: Settings → Accounts → Other Users
- Command:
```bash
lusrmgr.msc
```

### Groups
- Users can belong to multiple groups
- Groups define permissions

---

## Task 7: User Account Control (UAC)
- Protects system from unauthorized admin actions
- Prompts before high-privilege tasks
- Limits malware damage

- UAC stands for **User Account Control**

---

## Task 8: Settings vs Control Panel
- **Settings**: modern, user-friendly
- **Control Panel**: advanced system configuration
- They are interconnected

**Control Panel View**
- Change view to: `Small icons`
- Last option: **Windows Defender Firewall**

---

## Task 9: Task Manager
- View running processes
- Monitor CPU, memory, disk, network
- View users, services, and performance

### Open Task Manager
- Search
- Right-click taskbar
- Keyboard shortcut:

```
Ctrl + Shift + Esc
```

---
