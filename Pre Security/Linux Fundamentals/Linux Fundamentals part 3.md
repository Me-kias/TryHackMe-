# Linux Fundamentals Part 3 – Notes

---

## Task 1: Introduction

- Final room in the Linux Fundamentals series
- Focuses on:
  - Useful day-to-day Linux utilities
  - Terminal text editors
  - Automation basics
  - Package management
  - Service & application logging

---

## Task 2: Deploy Your Linux Machine

- Start the attached machine in TryHackMe
- SSH into the target machine:
```bash
ssh tryhackme@<TARGET_IP>
```
- Password:
```
tryhackme
```
- Do NOT use someone else’s IP
- If SSH issues occur, review Linux Fundamentals Part 2

---

## Task 3: Terminal Text Editors

### Why Text Editors?
- `echo` + redirection is inefficient for multi-line files
- Text editors make editing scripts, configs, and notes easier

---

### Nano (Beginner Friendly)

Create or edit a file:
```bash
nano filename
```

- If file doesn’t exist, it will be created on save
- Use arrow keys to move
- Enter key = new line

#### Common Nano Shortcuts
- `CTRL + X` → Exit
- `CTRL + W` → Search
- `CTRL + O` → Save
- Prompts to save changes if file was modified

Nano is:
- Easy to use
- Commonly installed
- Great for quick edits

---

### Vim (Advanced)

- More powerful but steeper learning curve
- Usually installed by default
- Popular with developers
- Features:
  - Heavy customization
  - Syntax highlighting
  - Works in almost all terminals

💡 Recommended to learn basics at minimum  
TryHackMe has a dedicated Vim room

---

### Create a File Using Nano

```bash
nano hello
```
Add text:
```
hello world
```

Save and exit:
- `CTRL + X`
- `Y`
- Enter

Check file:
```bash
ls
file hello
```

---

### Task Question

Edit `task3` using nano to find the flag:
```
THM{text_editors}
```

---

## Task 4: General / Useful Utilities

---

### Downloading Files with `wget`

Download files via HTTP/HTTPS:
```bash
wget http://example.com/file.txt
```

- Downloads to current directory
- Shows progress bar
- Very common in CTFs and pentesting

---

### Transferring Files with `scp` (SSH Copy)

Securely copy files between machines.

#### Local → Remote
```bash
scp important.txt user@<IP>:/path/to/destination
```

#### Remote → Local
```bash
scp user@<IP>:/path/to/file ./newname
```

- Uses SSH authentication
- Encrypted
- Similar to combining `ssh` + `cp`

---

### Serving Files with Python HTTP Server

Ubuntu comes with Python 3 installed.

Start a web server:
```bash
python3 -m http.server
```

- Serves files from current directory
- Default port: `8000`
- Terminal will be occupied while running

Change port:
```bash
python3 -m http.server 9000
```

---

### Download from Python Web Server

From another terminal or machine:
```bash
wget http://<IP>:8000/filename
```

⚠️ You must know the exact filename (no directory listing)

---

### Task Exercise

1. Start Python HTTP server in home directory
2. Download `.flag.txt` using `wget`
3. Read the file:
```bash
cat .flag.txt
```

Flag:
```
THM{wget_web_server}
```

Stop server:
```bash
CTRL + C
```

---

## Key Takeaways

- `nano` = easy, fast text editing
- `vim` = powerful, always available
- `wget` = download files from the web
- `scp` = transfer files securely over SSH
- `python3 -m http.server` = quick file hosting
- These tools are used constantly in labs & real systems

---

Next: **Processes 101**
