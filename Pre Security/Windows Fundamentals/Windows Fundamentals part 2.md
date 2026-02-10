
## TASK 1 – INTRODUCTION

- Start both machines (AttackBox + Windows machine).
- If using browser-based machines, click the Windows machine directly.
- No RDP/XFreeRDP needed when using the browser.
- Once connected to the Windows machine, mark Task 1 as complete.



## TASK 2 – SYSTEM CONFIGURATION (msconfig)

Purpose:
- Advanced troubleshooting
- Diagnose startup issues

How to open:
- Search: System Configuration
- Command: msconfig

Main Tabs:
- General: Startup selection (Normal, Diagnostic, Selective)
- Boot: Boot options (Safe boot, No GUI boot, etc.)
- Services: Lists system services
- Startup: Startup programs (handled via Task Manager)
- Tools: Quick access to system tools (e.g., Control Panel)

Command to open Control Panel:
- control.exe

Task 2 complete after reviewing tabs.


## TASK 3 – UAC SETTINGS

Purpose:
- Control User Account Control notifications

How to open:
- Search: Change UAC settings
- Command: UserAccountControlSettings.exe

Notes:
- Slider controls how often Windows notifies you
- Default: Notify when apps try to make changes
- Higher = more secure, Lower = less prompts

Task 3 complete after reviewing settings.



## TASK 4 – COMPUTER MANAGEMENT

How to open:
- Search: Computer Management
- Command: compmgmt.msc

Sections Reviewed:

1. System Tools
----------------
- Task Scheduler
  - Windows equivalent of cron jobs
  - Example task:
    - GoogleUpdateTaskMachineUA
    - Runs daily at 6:15 AM

- Event Viewer
  - Event types:
    - Error
    - Warning
    - Information
    - Success Audit
    - Failure Audit
  - Standard logs:
    - Application
    - Security
    - System

- Shared Folders
  - Shares
  - Sessions
  - Open Files
  - Hidden shared folder: SharedFolder$

- Local Users and Groups
  - Covered in Windows Fundamentals 1

- Performance
  - Performance Monitor
  - Device Manager

2. Storage
-----------
- Disk Management
  - View disks and volumes
  - Extend/Shrink volumes
  - Right-click volumes or use Action pane

3. Services and Applications
----------------------------
- Services
  - Enable/disable services
  - View properties and startup type

- WMI Control
  - Deprecated
  - Replaced by PowerShell

Questions & Answers:
- Command to open Computer Management:
  compmgmt.msc

- Google Update task time:
  6:15 AM

- Hidden shared folder name:
  SharedFolder$

## TASK 5 – SYSTEM INFORMATION

How to open:
- Search: System Information
- Command: msinfo32.exe

Sections:
- System Summary
- Hardware Resources
- Components
- Software Environment

Important:
- Environment Variables located under Software Environment
- Can also access via:
  - Search: Environment Variables
  - Edit environment variables for your account

Search feature:
- Use "Find" to locate items like IP Address

Questions & Answers:
- Command to open System Information:
  msinfo32.exe

- System Name:
  THM-WINFUN2

- Value of ComSpec:
  C:\Windows\System32\cmd.exe


## TASK 6 – RESOURCE MONITOR

How to open:
- Search: Resource Monitor
- Command: resmon.exe

Tabs:
- CPU
- Memory
- Disk
- Network

Purpose:
- View per-process system usage
- Filter activity by process

Question:
- Command to open Resource Monitor:
  resmon.exe

## TASK 7 – COMMAND PROMPT
Common Commands:
- hostname        → Shows computer name
- whoami          → Shows current user
- ipconfig        → Network info
- ipconfig /all   → Detailed network info
- cls             → Clear screen
- netstat         → Network connections
- netstat /?      → Netstat help

Help System:
- command /?      → Shows usage
- net help        → Help for net commands

Examples:
- net user        → List users
- net user /?     → User command help

Questions & Answers:
- Full command for Internet Protocol configuration:
  ipconfig

- Show detailed IP info:
  ipconfig /all
  
## TASK 8 – REGISTRY EDITOR
Purpose:
- View/Edit Windows Registry
- Stores system, user, hardware, and application settings

Warning:
- Changes can break the system

How to open:
- Search: Registry Editor
- Command: regedit

Question:
- Command to open Registry Editor:
  regedit

## TASK 9 – CONCLUSIO
- Completed Windows Fundamentals 2
- Topics covered:
  - System tools
  - Configuration utilities
  - Monitoring
  - Command line basics
  - Registry
- Next step:
  - Windows Fundamentals 3
========================
