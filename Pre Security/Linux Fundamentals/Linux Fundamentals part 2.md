# Linux Fundamentals Part 2 — TryHackMe Notes

Focus: SSH, flags, filesystem commands, permissions, and common directories.

---

## Task 1: Introduction

- This room continues **Linux Fundamentals Part 1**
- Focuses on:
  - SSH access to remote machines
  - Using command flags & arguments
  - File system interaction
  - File permissions
  - Running scripts and executables

---

## Task 2: Accessing Linux Machine Using SSH

### What is SSH?
- SSH = **Secure Shell**
- Used to remotely access and control another machine
- Encrypted communication using cryptography
- Common in real-world Linux administration & hacking

---

## Task 3: Introduction to Flags and Switches

Most Linux commands support **arguments**, commonly called **flags** or **switches**.
These allow you to change or extend how a command behaves.

Flags are usually identified by:
- A single hyphen (`-`)
- Or double hyphens (`--`)

If no flag is provided, the command runs with its **default behavior**.

---

## Using Flags with Commands

### Example: `ls`

# Linux Fundamentals – Filesystem, Permissions & Common Directories

These notes cover filesystem interaction, permissions, users, and common Linux directories.  
Useful for beginners, CTFs, and TryHackMe-style labs.

---

## Task 4: Filesystem Interaction (Continued)

### Creating Files & Directories

#### `touch`
Creates an empty file.
```bash
touch note
```
> `touch` only creates a blank file.  
To add content, use `echo`, `nano`, `vim`, etc.

#### `mkdir`
Creates a directory.
```bash
mkdir my_directory
```

---

### Removing Files & Directories

#### `rm`
Removes a file:
```bash
rm note
```

#### `rm -r`
Removes a directory **and all its contents** (recursive).
```bash
rm -r my_directory
```
⚠️ Be careful — this permanently deletes everything inside.

---

### Copying & Moving Files

#### `cp` (copy)
Copies a file and creates a new one.
```bash
cp note note2
```

#### `mv` (move / rename)
Moves a file OR renames it.
```bash
mv note2 note3
```
Move file into a directory:
```bash
mv myfile myfolder/
```

---

### Determining File Type

Linux does **not require file extensions**.

Use `file` to identify what a file actually is:
```bash
file unknown1
```
Example output:
```
ASCII text
```

Very useful in CTFs when files have no extension.

---

### Viewing File Contents

```bash
cat myfile
```

Example flag:
```
THM{filesystem}
```

---

## Task 5: Permissions 101

### Viewing Permissions

```bash
ls -l
```

Key columns:
```
-rwxr--r--
```

Breakdown:
- **First character**
  - `-` = file
  - `d` = directory
- **Owner permissions** (rwx)
- **Group permissions** (rwx)
- **Others permissions** (rwx)

### Permission Letters
- `r` = read
- `w` = write
- `x` = execute
- `-` = permission not allowed

Example:
```
-rw-r--r--
```
- Owner: read + write
- Group: read only
- Others: read only

---

### Users & Groups

- Every user has a **matching group** by default
- Permissions can differ between:
  - Owner
  - Group
  - Everyone else

This allows granular access control.

---

### Switching Users

#### `su`
Switch user (requires password):
```bash
su user2
```

#### `su -l`
Login shell (recommended):
```bash
su -l user2
```
✔ Loads the user’s environment  
✔ Moves you to their home directory  

---

### Reading Restricted Files

If permissions allow:
```bash
cat important
```

Example flag:
```
THM{su_user}
```

---

## Task 6: Common Linux Directories

### `/etc`
- System configuration files
- Important files:
  - `/etc/passwd`
  - `/etc/shadow`
  - `/etc/sudoers`
⚠️ `shadow` should NOT be readable by normal users

---

### `/var`
- Variable data used by services
- Logs, databases, app data

#### `/var/log`
- Stores system and application logs

---

### `/root`
- Home directory of the **root user**
- NOT `/home/root`

---

### `/tmp`
- Temporary storage
- Cleared on reboot
- **Anyone can write here**
- Great for scripts during pentesting
- ❌ Do NOT store important files

---

## Quick Answers Recap

- Logs directory:  
  ```
  /var/log
  ```

- Temp directory (cleared on restart):  
  ```
  /tmp
  ```

- Root user home directory:  
  ```
  /root
  ```

---

## Final Notes

- Linux permissions are powerful and flexible
- Practice these commands until they feel natural
- Take notes (seriously, it helps)
- These basics show up **constantly** in CTFs and real systems

Next up: **Linux Fundamentals Part 3** 🚀  
Happy hacking 🐧


