# TryHackMe – Linux Fundamentals Part 1 (Notes)


## Task 1: Introduction

Linux is an operating system, just like:
- Windows
- macOS
- iOS

Linux is extremely popular and powers:
- Websites and servers
- Android devices
- Smart cars
- Game consoles
- Supercomputers
- Embedded systems

Linux is:
- Lightweight
- Highly customizable
- Common in cybersecurity and penetration testing

This room:
- Covers Linux basics
- Uses an interactive terminal
- Teaches core commands
- Introduces users, groups, and filesystem navigation

---

## Task 2: A Bit of Background on Linux

### Where Linux is used
- Web servers (Apache, Nginx)
- Car infotainment systems
- POS systems (cash registers)
- Traffic light controllers
- Industrial sensors
- Embedded devices

You probably use Linux every day without realizing it.

---

### Linux distributions (distros)

Linux is an **umbrella term** for many operating systems based on **Unix**.

Different Linux distributions exist because:
- Unix is open source
- Systems need different features

Common distros:
- Ubuntu
- Debian
- Alpine

Ubuntu:
- Very common
- Can be a server or desktop
- Runs on very low resources
- Used throughout this series

---

### Question
- Year Linux was first released: **1991**

---

## Task 3: Interacting with Your First Linux Machine (In-Browser)

- Each task launches an Ubuntu machine in your browser
- Click **Start Machine** to begin

Machine info:
- **IP address** → how you identify the machine
- **Timer** → machines run for 2 hours
- Can extend or terminate early

Terminal access opens automatically once ready.

---

## Task 4: Running Your First Few Commands

Linux systems often:
- Have no GUI
- Are controlled entirely via the terminal

The terminal:
- Is text-based
- Very powerful
- Faster than GUI for many tasks

---

### Command: `echo`
- Outputs text to the terminal
- Useful for debugging and scripting

Example:
```bash
echo "Hello World"
