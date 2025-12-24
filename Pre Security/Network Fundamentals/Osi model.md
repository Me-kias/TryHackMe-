# OSI Model – Human Notes (Easy & Important)

## What is the OSI Model?
- **OSI** = Open Systems Interconnection
- A **7-layer model** that explains how data moves across a network
- Used for **understanding** and **troubleshooting** networks
- Data moves through layers using **encapsulation** (info added at each layer)

---

## OSI Layers (Top → Bottom)

### Layer 7 – Application
- What the **user interacts with**
- Examples:
  - Web browsers
  - Email
  - FTP
- Uses **GUI** (Graphical User Interface)

---

### Layer 6 – Presentation
- **Translates & formats data**
- Makes sure data looks the same on all devices
- Handles **encryption** (e.g. HTTPS)
- Main job: **standardization**

---

### Layer 5 – Session
- **Creates and manages sessions** (connections)
- Keeps devices in sync
- Breaks data into **packets**
- If connection drops, only missing packets resend

---

### Layer 4 – Transport
- Controls **how data is sent**
- Uses two protocols:

#### TCP (Transmission Control Protocol)
- Reliable & accurate
- Error checking
- Slower
- Used for:
  - Email
  - File downloads
  - Web browsing

#### UDP (User Datagram Protocol)
- Fast, no checks
- Data may be lost
- Used for:
  - Video streaming
  - Voice calls
  - Online games

---

### Layer 3 – Network
- Handles **routing**
- Chooses best path for data
- Uses **IP addresses**
- Devices: **Routers**
- Protocols:
  - OSPF (Open Shortest Path First)
  - RIP (Routing Information Protocol)

---

### Layer 2 – Data Link
- Uses **MAC addresses**
- Adds physical address to data
- Hardware: **NIC** (Network Interface Card)
- MAC = physical address (factory set)

---

### Layer 1 – Physical
- Actual **hardware**
- Cables, signals, electricity
- Uses **binary (0s and 1s)**
- Example: **Ethernet cables**

---

## Easy Layer Order (Bottom → Top)
**Physical → Data Link → Network → Transport → Session → Presentation → Application**

---

## Quick Answers
- OSI layers = **7**
- Encapsulation = adding info at each layer
- GUI = Graphical User Interface
- Reliable protocol = **TCP**
- Fast protocol = **UDP**
- Logical address = **IP**
- Physical address = **MAC**
