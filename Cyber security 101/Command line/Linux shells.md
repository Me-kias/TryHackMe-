# Linux Shells – Simple Notes (TryHackMe Room)

---

## 🧠 Task 1 – What is a Shell?

- The **shell** is the middleman between the user and the operating system.
- Two main ways to interact:
  - **GUI** (Graphical User Interface)
  - **CLI** (Command Line Interface)
- The shell is the bigger concept. CLI is just one way to use a shell.

### Learning Goals
- Understand the Linux shell
- Learn basic commands
- Learn different types of shells
- Write simple shell scripts

---

## 💻 Task 2 – Basic Commands

### `pwd`
- Print Working Directory  
- Shows where you are.

### `ls`
- Lists files and folders in the current directory.

### `cd foldername`
- Change directory.
- `cd ..` → go back one folder.

### `cat filename`
- Shows content inside a file.

### `grep "word" filename`
- Searches for a word inside a file.

### `history`
- Shows previously executed commands in the current session.

### Default Shell
- Most Linux systems use **bash** (Bourne Again Shell) by default.

---

## 🐚 Task 3 – Types of Shells

### 1️⃣ bash
- Default shell in most Linux systems.
- Supports scripting.
- Has tab completion.
- Has command history.

### 2️⃣ fish (Friendly Interactive Shell)
- Beginner friendly.
- Syntax highlighting.
- Auto spell correction.
- More user-friendly features.

### 3️⃣ zsh (Z Shell)
- Very customizable.
- Supports plugins.
- Can be styled heavily.
- Often used in Kali Linux.

---

### Useful Shell Commands

Check your current shell:
```bash
echo $SHELL
