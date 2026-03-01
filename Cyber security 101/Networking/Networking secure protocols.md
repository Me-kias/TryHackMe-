# Networking Secure Protocols – Human Notes

---

# Task 1 – Introduction

This room builds on previous networking rooms.

You should already know:
- HTTP
- FTP
- SMTP
- POP3
- IMAP
- Telnet

Now we learn how to make these **secure**.

---

## What Makes a Protocol Secure?

Secure = **Encrypted**

If data is encrypted:
- Attackers cannot read it
- Attackers cannot modify it

Example:

| Insecure | Secure |
|-----------|---------|
| HTTP | HTTPS |
| FTP | FTPS / SFTP |
| IMAP | IMAPS |
| POP3 | POP3S |
| SMTP | SMTPS |
| Telnet | SSH |

The “S” usually means **Secure**.

---

# Task 2 – TLS (Transport Layer Security)

## What is TLS?

TLS = Transport Layer Security

It encrypts communication between:
- Client
- Server

Before TLS, there was:
SSL (Secure Sockets Layer)

TLS replaced SSL because it is stronger and safer.

---

## What Does TLS Do?

TLS provides:

- Encryption (no one can read data)
- Integrity (data cannot be changed secretly)
- Authentication (server proves who it is)

---

## TLS Handshake (Simple Idea)

Before sending encrypted data:

1. Client says: "Can we talk securely?"
2. Server says: "Yes"
3. They agree on encryption method
4. Then communication starts

This is called the **TLS Handshake**

---

## Certificates & Certificate Authority (CA)

To prove a server is real:

- Server requests a certificate
- Certificate Authority (CA) verifies it
- CA signs the certificate
- Now users trust that server

When you visit a secure website, your browser checks:
“Is this certificate signed by a trusted CA?”

---

### Self-Signed Certificate

Self-signed = server signs its own certificate.

This is NOT trusted.

Because:
There is no third-party verification.

---

# Task 3 – HTTPS

## HTTP (Port 80)

- Not encrypted
- You can read traffic in Wireshark
- Uses TCP

Flow:
1. TCP 3-way handshake
2. Data transfer
3. Close connection

---

## HTTPS (Port 443)

HTTPS = HTTP + TLS

Flow:
1. TCP handshake
2. TLS handshake
3. Encrypted data transfer

In Wireshark:
- You see TLS packets
- Data looks unreadable

Unless you have the encryption key.

---

## Important

HTTP → You can see:
- GET requests
- Login credentials
- Everything

HTTPS → You see:
- Encrypted TLS packets

---

# Task 4 – Secure Versions of Protocols

| Protocol | Insecure Port | Secure Port |
|----------|--------------|-------------|
| HTTP | 80 | 443 |
| FTP | 21 | 990 |
| Telnet | 23 | 22 (SSH) |
| SMTP | 25 | 465 / 587 |
| POP3 | 110 | 995 |
| IMAP | 143 | 993 |

Memorize these for exams and SOC jobs.

---

# Task 5 – SSH

## What is SSH?

SSH = Secure Shell  
Port: 22

It replaced Telnet (Port 23).

---

## Why SSH?

SSH provides:

- Secure login
- Encryption
- Protection against man-in-the-middle attacks
- Secure tunneling

---

## SSH Tunnel

SSH can create a secure tunnel.

Even insecure protocols can become secure if sent through SSH.

---

## OpenSSH

OpenSSH is the most used implementation today.

---

# Task 6 – SFTP & FTPS

Two secure versions of FTP:

---

## SFTP

- Uses SSH
- Easier setup
- No certificate needed
- Port 22

---

## FTPS

- Uses TLS
- Requires certificate
- Port 990

---

## Key Difference

SFTP → SSH-based  
FTPS → TLS-based  

Both are secure file transfer methods.

---

# Task 7 – VPN

VPN = Virtual Private Network

---

## How VPN Works

1. Your device encrypts traffic
2. Traffic goes to VPN server
3. VPN server decrypts it
4. Then sends it to internet

Everything between:
You ↔ VPN Server  
is encrypted

---

## Company Example

Remote employee:
- Uses VPN
- Connects to company network securely

---

## Personal VPN Example

If you choose a Japan server:

- Your traffic goes to Japan VPN server
- Netflix sees request from Japan
- You can watch Japan-only content

VPN hides:
- Your real IP
- Your location

---

# Task 8 – Decrypting TLS Traffic

In Wireshark:

TLS traffic looks unreadable.

But if you have:
- The encryption key

You can:
- Add key file in TLS preferences
- Decrypt traffic
- See HTTP requests
- See login credentials

---

## Important Lesson

HTTPS is secure.

But:
If attacker gets encryption key,
Traffic can be decrypted.

---

# Why This Room Matters (SOC Perspective)

As a SOC Analyst you must:

- Recognize encrypted vs unencrypted traffic
- Know default ports
- Detect insecure protocols
- Understand TLS handshakes
- Investigate suspicious traffic
- Analyze packet captures
- Identify credential leaks

---

# Final Big Picture

Modern internet security depends on:

- TLS
- Certificates
- SSH
- Secure file transfer
- VPN encryption

Without these:
Passwords, banking data, emails would be visible.
