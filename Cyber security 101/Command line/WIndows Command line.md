# 🖥️ TryHackMe – Windows Command Line Room Notes

These are my notes from completing the Windows Command Line room on TryHackMe.  
This room focuses on understanding the Windows Command Prompt (CMD) and how to use it for system interaction, networking, file management, and process control.

---

# 1️⃣ Introduction – GUI vs CLI

### GUI (Graphical User Interface)
- Uses icons, windows, mouse
- Beginner friendly
- Higher resource usage

### CLI (Command Line Interface)
- Text-based
- Faster and lightweight
- Better for automation
- Easier remote management

Windows default command line interpreter:
```
cmd.exe
```

---

# 2️⃣ Environment Variables & PATH

To view environment variables (including PATH):

```
set
```

The PATH variable determines where Windows looks for executable commands.  
If a command isn’t in PATH, it won’t run unless you specify the full location.

---

# 3️⃣ System Information Commands

Check Windows version:
```
ver
```

Get detailed system information:
```
systeminfo
```

Important details you can gather:
- OS Name
- OS Version
- Hostname
- System Manufacturer
- Installed memory
- Network information

If output is long, use pagination:

```
systeminfo | more
```

Controls:
- Space → next page
- Enter → next line
- Ctrl + C → exit

Get help for commands:
```
help
systeminfo /?
```

Clear screen:
```
cls
```

---

# 4️⃣ Networking Commands

Basic network information:
```
ipconfig
ipconfig /all
```

Useful for finding:
- IPv4 address
- Subnet mask
- Default gateway
- MAC address (Physical Address)

Test connectivity:
```
ping example.com
```

Trace packet route:
```
tracert example.com
```

DNS lookup:
```
nslookup example.com
```

View active connections:
```
netstat
```

Common flags:
```
netstat -a    → all connections
netstat -b    → show executable
netstat -o    → show PID
netstat -n    → numerical output
```

Most useful combo:
```
netstat -abno
```

---

# 5️⃣ File & Directory Management

Show current directory:
```
cd
```

List files:
```
dir
```

Show hidden files:
```
dir /a
```

Recursive listing:
```
dir /s
```

Tree view:
```
tree
```

Change directory:
```
cd foldername
```

Go back one directory:
```
cd ..
```

Create directory:
```
mkdir foldername
```

Remove directory:
```
rmdir foldername
```

---

# 6️⃣ Working with Files

View file contents:
```
type filename.txt
```

With pagination:
```
type filename.txt | more
```

Copy file:
```
copy source.txt destination.txt
```

Move file:
```
move file.txt ..
```

Delete file:
```
del filename.txt
```
or
```
erase filename.txt
```

Wildcard usage:
```
copy *.md markdown\
```

`*` matches anything.

---

# 7️⃣ Managing Processes

List running processes:
```
tasklist
```

Filter processes (example: Notepad):
```
tasklist /FI "IMAGENAME eq notepad.exe"
```

Kill a process by PID:
```
taskkill /PID 1516
```

---

# 8️⃣ Extra Useful Commands

Check disk:
```
chkdsk
```

List installed drivers:
```
driverquery
```

Scan system files:
```
sfc /scannow
```

---

# 9️⃣ Shutdown & Restart

Shutdown:
```
shutdown /s
```

Restart:
```
shutdown /r
```

Abort scheduled shutdown:
```
shutdown /a
```

---

# 🔥 Key Takeaways

- `cmd.exe` is the default Windows command interpreter
- `systeminfo` gives detailed OS data
- `ipconfig /all` reveals MAC address
- `netstat -abno` helps identify listening services
- `tasklist /FI` filters processes
- `taskkill /PID` terminates processes
- `shutdown /r` restarts the system
- `shutdown /a` cancels shutdown

---

Next step: Move on to PowerShell to expand command-line skills.

