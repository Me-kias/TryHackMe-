# Nmap Basics — Human Notes (TryHackMe)

## Task 1 — Intro to Nmap

Nmap is basically the go-to tool for network scanning in cybersecurity.

You can use it to:
- Find devices/hosts on a network
- Check open ports
- Identify running services
- Detect service versions
- Guess operating systems
- Scan entire networks/subnets

Example:
```bash
nmap 10.10.10.5
```

Nmap is better than doing manual stuff like ping scans or telnet checks because it automates everything and is way faster.

### Main learning goals
- Discover live hosts
- Scan ports
- Understand different scan types
- Detect service versions
- Control scan speed/timing
- Save/output scan results

---

# Task 2 — Host Discovery

Nmap can discover devices that are alive on a network.

Basic syntax:
```bash
nmap <IP>
```

Example:
```bash
nmap 10.10.10.5
```

You can also scan:
- Multiple IPs
- IP ranges
- Entire subnets

Examples:
```bash
nmap 10.10.10.1-20
```

CIDR notation:
```bash
nmap 10.10.10.0/24
```

---

## `-sn` option (Ping Scan / Host Discovery)

```bash
nmap -sn 10.10.10.0/24
```

This tells Nmap:
> "Only tell me what hosts are up."

No port scanning.

Nmap does more than normal ping:
- ICMP requests
- TCP checks
- Timestamp requests
- Other host discovery methods

So it’s smarter than regular ping.

---

## Root / sudo matters

Some Nmap features need elevated privileges.

Use:
```bash
sudo nmap
```

Without sudo:
- Some scans won’t work properly
- Nmap may downgrade scan types

---

## `-sL` option (List Scan)

```bash
nmap -sL 10.10.10.0/24
```

Does NOT scan anything.

It only lists targets that WOULD be scanned.

Useful to verify you’re scanning the correct range.

---

## CIDR quick note

Example:
```bash
10.10.10.0/27
```

- `/27` means 27 bits are fixed
- Leaves 5 host bits
- `2^5 = 32` addresses total
- 1 is network address

So:
- usable range ends at `.31`

---

# Task 3 — Port Scanning

If you don’t use `-sn`, Nmap automatically scans ports.

---

## TCP Connect Scan (`-sT`)

```bash
nmap -sT 10.10.10.5
```

Full TCP handshake:
1. SYN
2. SYN/ACK
3. ACK

Then connection closes.

More detectable because full connection happens.

---

## SYN Scan / Stealth Scan (`-sS`)

```bash
sudo nmap -sS 10.10.10.5
```

This is the popular one.

Flow:
1. SYN
2. SYN/ACK
3. RST

Connection never fully established.

Benefits:
- Faster
- Less logging
- More stealthy

Needs sudo/root.

---

## UDP Scan (`-sU`)

```bash
sudo nmap -sU 10.10.10.5
```

Used for UDP services like:
- DNS
- DHCP
- NTP
- VoIP

UDP scans are slower and less reliable because UDP has no handshake.

---

# Port Selection

Default:
- scans top 1000 ports

Fast scan:
```bash
nmap -F 10.10.10.5
```

Top 100 ports only.

---

## Specific ports

Single port:
```bash
nmap -p 80 10.10.10.5
```

Range:
```bash
nmap -p 1-1000 10.10.10.5
```

All ports:
```bash
nmap -p- 10.10.10.5
```

There are 65535 ports total, so full scans take longer.

---

# Task 4 — Version Detection

## OS Detection (`-O`)

```bash
sudo nmap -O 10.10.10.5
```

Attempts to identify operating system.

Not always 100% accurate.

---

## Service Version Detection (`-sV`)

```bash
nmap -sV 10.10.10.5
```

Shows:
- service name
- version number

Example:
```text
22/tcp open ssh OpenSSH 8.2
```

Very useful during enumeration.

---

## Aggressive Scan (`-A`)

```bash
sudo nmap -A 10.10.10.5
```

Enables:
- OS detection
- version detection
- scripts
- traceroute

Good for quick recon.

BUT:
- loud/noisy
- easy to detect

---

## Skip Host Discovery (`-Pn`)

```bash
nmap -Pn 10.10.10.5
```

Tells Nmap:
> "Assume host is up."

Useful when:
- ping is blocked
- firewall drops discovery packets

Normally Nmap:
1. discovers hosts
2. THEN scans ports

`-Pn` skips step 1.

---

# Task 5 — Timing & Speed

Timing templates:
```bash
-T0 to -T5
```

### Levels
| Option | Name |
|---|---|
| T0 | paranoid |
| T1 | sneaky |
| T2 | polite |
| T3 | normal |
| T4 | aggressive |
| T5 | insane |

Default:
```bash
-T3
```

---

## Why timing matters

Fast scans:
- quicker results
- easier to detect

Slow scans:
- stealthier
- blend into network traffic

Example:
```bash
nmap -T4 10.10.10.5
```

Aggressive scan speed.

---

## Packet rate controls

Minimum rate:
```bash
--min-rate 100
```

Controls packet sending speed.

Higher values:
- faster scans
- more noise

---

## Host timeout

```bash
--host-timeout 30s
```

Maximum wait time for a host response.

Useful on slow or unreliable networks.

---

# Task 6 — Output Control

## Verbose mode (`-v`)

```bash
nmap -v 10.10.10.5
```

More details during scan.

More verbosity:
```bash
-vv
-vvv
```

---

## Debugging (`-d`)

```bash
nmap -d 10.10.10.5
```

Super detailed debugging output.

Can go up to:
```bash
-d9
```

Usually overkill unless troubleshooting.

---

# Saving Results

## Normal output
```bash
-oN scan.txt
```

## XML output
```bash
-oX scan.xml
```

## Grepable output
```bash
-oG scan.gnmap
```

## Save ALL formats
```bash
-oA scan
```

Creates:
- `scan.nmap`
- `scan.xml`
- `scan.gnmap`

Very useful for reporting or importing into tools later.

---

# Task 7 — Final Important Notes

## Use sudo whenever possible

Without sudo/root:
- SYN scans may not work
- Nmap falls back to Connect Scan (`-sT`)

Example:
```bash
sudo nmap -sS 10.10.10.5
```

Better than:
```bash
nmap 10.10.10.5
```

because normal users usually get:
- TCP Connect Scan (`-sT`)

instead of:
- SYN Scan (`-sS`)

---

# Quick Cheat Sheet

## Host Discovery
```bash
nmap -sn 10.10.10.0/24
```

## SYN Scan
```bash
sudo nmap -sS 10.10.10.5
```

## UDP Scan
```bash
sudo nmap -sU 10.10.10.5
```

## Version Detection
```bash
nmap -sV 10.10.10.5
```

## OS Detection
```bash
sudo nmap -O 10.10.10.5
```

## Aggressive Scan
```bash
sudo nmap -A 10.10.10.5
```

## Scan All Ports
```bash
nmap -p- 10.10.10.5
```

## Faster Scan
```bash
nmap -T4 10.10.10.5
```

## Skip Ping
```bash
nmap -Pn 10.10.10.5
```

## Save Results
```bash
nmap -oA scan 10.10.10.5
```
