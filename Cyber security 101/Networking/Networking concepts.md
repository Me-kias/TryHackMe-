# 🌐 Networking Concepts – TryHackMe Notes

These are structured notes from the **Networking Concepts** room on TryHackMe.  

---

# 📚 Task 1 – Introduction

## Prerequisites
- Basic understanding of networking
- Familiarity with Linux/Windows command line

---

# 🏗️ Task 2 – The OSI Model

**OSI = Open Systems Interconnection Model**

A conceptual model describing how network communication works in 7 layers.

> ⚠️ The OSI model is theoretical. Real-world networking uses the TCP/IP model.

---

## 🔢 The 7 OSI Layers

### 1️⃣ Physical Layer
- Physical transmission of bits (1s and 0s)
- Wires, fiber optics, Wi-Fi signals

---

### 2️⃣ Data Link Layer
- Communication between devices on the same network
- Uses **MAC addresses**
- Example format:
  ```
  00:1A:2B:3C:4D:5E
  ```
- First half = vendor
- Second half = unique device identifier

---

### 3️⃣ Network Layer
- Handles routing between networks
- Uses **IP addresses**
- Routers operate here

Layer 2 = MAC address  
Layer 3 = IP address

---

### 4️⃣ Transport Layer
- End-to-end communication
- Uses:
  - TCP
  - UDP

---

### 5️⃣ Session Layer
- Establishes and manages sessions
- Synchronizes communication
- Handles recovery if transmission fails

---

### 6️⃣ Presentation Layer
- Encoding
- Compression
- Encryption

Examples:
- ASCII
- Unicode
- SSL/TLS

---

### 7️⃣ Application Layer
- Closest to the end user
- Protocols:
  - HTTP
  - FTP
  - DNS
  - POP3

---

# 🔁 Task 3 – TCP/IP Model

The **TCP/IP model** is the real-world networking model.

## 4 Layers of TCP/IP

| TCP/IP Layer | OSI Equivalent |
|--------------|---------------|
| Link | Data Link |
| Internet | Network |
| Transport | Transport |
| Application | Session + Presentation + Application |

---

# 🌍 Task 4 – IP Addresses

An **IP address** uniquely identifies a device on a network.

## IPv4 Format
```
192.168.1.1
```

- 4 octets
- Each ranges from 0–255

---

## Reserved Addresses
- Network address (usually .0)
- Broadcast address (usually .255)

---

## Public vs Private IP

### 🌎 Public IP
- Unique worldwide
- Assigned to your router

### 🏠 Private IP
- Used inside local networks
- Can repeat across networks

### Private IP Ranges
```
10.0.0.0 – 10.255.255.255
172.16.0.0 – 172.31.255.255
192.168.0.0 – 192.168.255.255
```

---

# 🔀 Routing

Routers:
- Examine destination IP
- Forward packets hop-by-hop
- Operate at Layer 3

Think of it like a postal system for data.

---

# 🔄 Task 5 – TCP vs UDP

## 📦 UDP
- Fast
- No error checking
- No handshake
- Used for streaming, VoIP, gaming

Think: Someone talking nonstop without waiting.

---

## 🤝 TCP
- Reliable
- Error checking
- Uses 3-way handshake

### Three-Way Handshake
```
SYN → SYN-ACK → ACK
```

Used for:
- Web browsing
- File downloads
- Emails

---

## Ports
- Total ports: ~65,000
- Examples:
  - 80 → HTTP
  - 443 → HTTPS
  - 21 → FTP
  - 22 → SSH

---

# 📦 Task 6 – Encapsulation

Encapsulation = Wrapping data in layers as it moves down the stack.

## Process

1. Application Data
2. Add TCP/UDP Header → Segment/Datagram
3. Add IP Header → Packet
4. Add Ethernet/Wi-Fi Header → Frame

Receiver reverses the process (decapsulation).

---

## Data Unit Names

| Layer | Name |
|-------|------|
| Application | Data |
| Transport (TCP) | Segment |
| Transport (UDP) | Datagram |
| Network | Packet |
| Data Link | Frame |

---

# 🖥️ Task 7 – Telnet

Telnet connects to services via TCP.

### Example:
```
telnet <IP> 80
```

Used to interact with:
- Echo server (Port 7)
- Daytime server (Port 13)
- Web server (Port 80)

---

## Example HTTP Request via Telnet
```
GET / HTTP/1.1
Host: tnet.thm

```

Note:
- Press Enter twice
- Blank line ends request

---

# 🎯 Key Takeaways

- OSI = theoretical (7 layers)
- TCP/IP = real-world (4 layers)
- IP addresses identify devices
- TCP = reliable
- UDP = fast
- Encapsulation wraps data in layers
- Routers operate at Layer 3
- MAC addresses operate at Layer 2

---

# 🚀 Next Step

Continue with:
**Network Essentials (TryHackMe)**
