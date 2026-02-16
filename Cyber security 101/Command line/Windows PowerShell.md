# 🖥️ TryHackMe – Windows PowerShell Room Notes

These are my notes from completing the Windows PowerShell room on TryHackMe.  
PowerShell is much more powerful than the traditional Windows Command Prompt because it combines command-line functionality with scripting and object-oriented concepts.

---

# 1️⃣ Introduction

PowerShell is different from the traditional Windows Command Line (cmd).

It was created because system administration became too complex to manage efficiently using plain text-based commands. PowerShell introduces:

- Object-oriented output (not just text)
- Scripting capabilities
- Automation features
- Better filtering and pipeline handling

If CMD is basic text-based control, PowerShell is more like a scripting language mixed with a command line.

---

# 2️⃣ What Makes PowerShell Different?

The biggest difference:

 **Everything in PowerShell is an object.**

In CMD or Linux bash, commands return plain text.

In PowerShell, commands return objects that have:
- Properties (characteristics)
- Methods (actions)

Example:
If a “car” were an object:
- Properties → color, fuel level, model
- Methods → drive(), honk(), refuel()

This object-based system allows much more advanced filtering and manipulation of data.

The development approach used to build PowerShell is:
**Object-Oriented Programming**

---

# 3️⃣ PowerShell Basics

## Starting PowerShell

If you're inside Command Prompt:

```
powershell
```

You’ll know you’re inside PowerShell when you see:

```
PS C:\>
```

---

## Cmdlets (Command-Lets)

PowerShell uses a **Verb-Noun** format.

Examples:

```
Get-Content
Set-Location
Get-Command
Get-Help
```

Structure:
```
Verb-Noun
```

- Verb → Action
- Noun → Object being acted on

---

## Useful Basic Cmdlets

### List all available commands:
```
Get-Command
```

Filter by name:
```
Get-Command -Name Remove*
```

---

### Get help for a command:
```
Get-Help Get-Date
```

With examples:
```
Get-Help Get-Date -Examples
```

---

## Aliases

PowerShell includes aliases so you can use familiar commands:

| Alias | Actual Cmdlet |
|--------|--------------|
| ls | Get-ChildItem |
| cd | Set-Location |
| cat | Get-Content |
| echo | Write-Output |

Check aliases:
```
Get-Alias
```

---

# 4️⃣ File System Navigation

## List directory contents:
```
Get-ChildItem
```
or
```
ls
```

---

## Change directory:
```
Set-Location Documents
```
or
```
cd Documents
```

Go back:
```
cd ..
```

---

## Create new file:
```
New-Item -Path file.txt -ItemType File
```

Create directory:
```
New-Item -Path FolderName -ItemType Directory
```

---

## Remove item:
```
Remove-Item file.txt
```

---

## Copy item:
```
Copy-Item -Path file.txt -Destination backup.txt
```

---

## Move item:
```
Move-Item -Path file.txt -Destination Folder\
```

---

## Read file contents:
```
Get-Content file.txt
```
or
```
cat file.txt
```

---

# 5️⃣ Piping & Filtering

PowerShell uses `|` just like Linux.

Example:
```
Get-ChildItem | Sort-Object Length
```

Sort descending:
```
Get-ChildItem | Sort-Object Length -Descending
```

Get largest file:
```
Get-ChildItem | Sort-Object Length -Descending | Select-Object -First 1
```

---

## Filtering with Where-Object

Example:
Show only .txt files:

```
Get-ChildItem | Where-Object {$_.Extension -eq ".txt"}
```

Show files larger than 1000 bytes:

```
Get-ChildItem | Where-Object {$_.Length -gt 1000}
```

Operators:
- `-eq` → equal
- `-ne` → not equal
- `-gt` → greater than
- `-ge` → greater or equal
- `-lt` → less than
- `-le` → less or equal
- `-like` → pattern matching (use *)

---

## Search Inside Files

Similar to `grep`:

```
Select-String -Path file.txt -Pattern "word"
```

---

# 6️⃣ System & Network Information

## System info:
```
Get-ComputerInfo
```

Equivalent to:
```
systeminfo
```

---

## Local users:
```
Get-LocalUser
```

---

## Network configuration:
```
Get-NetIPConfiguration
```

IP addresses:
```
Get-NetIPAddress
```

---

# 7️⃣ Real-Time Monitoring

## Running processes:
```
Get-Process
```

## Services:
```
Get-Service
```

Filter service by display name:
```
Get-Service | Where-Object {$_.DisplayName -like "*merry*"}
```

---

## Network connections:
```
Get-NetTCPConnection
```

Important property:
```
OwningProcess
```

---

## File hash:
```
Get-FileHash file.txt
```

Useful for:
- Malware detection
- File integrity checking

---

# 8️⃣ Remote Execution & Scripting

PowerShell allows remote command execution.

Example:

```
Invoke-Command -ComputerName RoyalFortune -ScriptBlock {Get-Service}
```

Structure:
- `Invoke-Command`
- `-ComputerName`
- `-ScriptBlock { command }`

This executes commands remotely.

---

# 9️⃣ Why PowerShell Matters

PowerShell is powerful because it:

- Works with objects instead of text
- Allows automation
- Supports remote management
- Is heavily used in:
  - Blue Team (monitoring, incident response)
  - Red Team (enumeration, exploitation)
  - System administration

---

# 🔥 Key Takeaways

- Everything in PowerShell is an object.
- Cmdlets follow Verb-Noun structure.
- Pipelines allow powerful filtering.
- Where-Object is essential.
- Invoke-Command enables remote execution.
- Get-FileHash is useful for threat analysis.

---

PowerShell takes time to get comfortable with, but once it clicks, it becomes extremely powerful.

Next step: Practice combining cmdlets and building small scripts.
