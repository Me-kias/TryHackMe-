==============================
WINDOWS COMMAND LINE NOTES
==============================

1) GUI vs CLI
--------------------------------
GUI = Graphical User Interface (mouse, icons, windows)
CLI = Command Line Interface (text-based commands)

Why CLI is important:
- Uses fewer system resources
- Allows automation (scripts)
- Easier remote management
- Widely used in cybersecurity

Default Windows CLI:
cmd.exe


================================
BASIC SYSTEM INFORMATION
================================

ver
- Shows Windows version.

systeminfo
- Shows detailed system information:
  - OS version
  - Hostname
  - Domain
  - System architecture
  - Patch level
  - Boot time

help
command /?
- Shows help page for any command.

cls
- Clears the screen.

| (pipe)
- Sends output from one command into another.
Example:
systeminfo | more

more
- Displays output one page at a time.


================================
NETWORKING COMMANDS
================================

ipconfig
- Shows:
  - IP address
  - Subnet mask
  - Default gateway

ipconfig /all
- Shows:
  - MAC address
  - DNS servers
  - DHCP status
  - Full adapter details

ping <target>
- Tests connectivity to another machine.

tracert <target>
- Shows the path packets take to reach a target.

nslookup <domain>
- Converts domain to IP address.
- Used for DNS lookups.

netstat
- Shows active connections.

netstat -a
- Shows all connections and listening ports.

netstat -ano
- Shows:
  - All connections
  - Listening ports
  - Process ID (PID)
Important for identifying suspicious connections.


================================
FILE & DIRECTORY MANAGEMENT
================================

dir
- Lists files and folders.

dir /a
- Shows hidden files.

dir /s
- Shows files in current directory and subdirectories.

tree
- Displays folder structure visually.

cd
- Shows current directory.

cd <folder>
- Changes directory.

cd ..
- Goes back one directory.

mkdir <folder>
- Creates a folder.

rmdir <folder>
- Removes a folder.

type <file>
- Displays file contents.

copy <source> <destination>
- Copies a file.

move <file> <destination>
- Moves a file.

del <file>
erase <file>
- Deletes a file.

* (wildcard)
- Used to match multiple files.
Example:
copy *.md backup


================================
PROCESS MANAGEMENT
================================

tasklist
- Shows running processes.

tasklist /fi "imagename eq notepad.exe"
- Filters processes by name.

taskkill /PID <number>
- Terminates a process by PID.


================================
SYSTEM UTILITIES (Extra)
================================

chkdsk
- Checks disk for errors.

driverquery
- Shows installed device drivers.

sfc /scannow
- Scans and repairs corrupted system files.

shutdown /s
- Shuts down the system.

shutdown /r
- Restarts the system.

shutdown /a
- Aborts a scheduled shutdown.


================================
CORE SKILLS YOU MUST MASTER
================================

- Identify system info (systeminfo)
- Check network configuration (ipconfig /all)
- Test connectivity (ping)
- View open ports (netstat -ano)
- Navigate directories (cd, dir)
- Read files (type)
- List processes (tasklist)
- Kill processes (taskkill)
- Use help commands
- Use pipes and filtering

================================
END OF NOTES
================================
