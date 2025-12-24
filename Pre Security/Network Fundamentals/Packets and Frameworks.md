# Packets, Frames & TCP/IP
## Packets vs Frames
- **Packets** = data WITH IP address (Layer 3)
- **Frames** = data WITHOUT IP address (Layer 2)
- Think: **envelope inside another envelope**
- Process is called **encapsulation**
- Small pieces = less network congestion
- Data is rebuilt at destination (e.g. images load in parts)

### Packet headers (important bits)
- **TTL (Time To Live)** → stops packets looping forever
- **Checksum** → checks data integrity
- **Source IP** → where data came from
- **Destination IP** → where data is going

---

## TCP/IP Model
- A **simplified version of OSI**
- Has **4 layers**:
  1. Application
  2. Transport
  3. Internet
  4. Network Interface
- Uses **encapsulation** too

---

## TCP (Transmission Control Protocol)
- **Connection-based**
- Reliable & accurate
- Uses **Three-Way Handshake**
- Slower but safe
- Used for:
  - File transfer
  - Emails
  - Web pages

### TCP Important Headers
- Source port (random)
- Destination port (service port)
- Sequence number (order)
- Acknowledgement number
- **Checksum** (integrity)
- Flags (SYN, ACK, FIN, RST)

---

## Three-Way Handshake (VERY IMPORTANT)
1. **SYN** → “Can we talk?”
2. **SYN-ACK** → “Yes, ready”
3. **ACK** → “Confirmed”

Connection established ✅

### Closing TCP
- **FIN** → polite close
- **RST** → force close (error)

---

## UDP (User Datagram Protocol)
- **Stateless**
- No handshake
- No guarantees
- Faster
- Used for:
  - Video calls
  - Streaming
  - Online games

---

## Ports (Basics)
- Range: **0–65535**
- **0–1024 = common ports**
- Ports tell data **which app to go to**

### Important Ports to Remember
- **FTP** → 21
- **SSH** → 22
- **HTTP** → 80
- **HTTPS** → 443
- **SMB** → 445
- **RDP** → 3389

> Web servers can run on other ports (e.g. 8080), but defaults are assumed unless specified.

---

## Key Answers Recap
- Data without IP = **Frame**
- Data with IP = **Packet**
- Integrity check header = **Checksum**
- TCP handshake order = **SYN → SYN-ACK → ACK**
- File transfer protocol = **TCP**
- Video call protocol = **UDP**
