# Intro to LAN – Quick Notes (Human Style)

## LAN & Topologies
- **LAN** = Local Area Network
- **Topology** = how devices are connected

### Star Topology
- All devices connect to a **central switch/router**
- ✅ Reliable, easy to add devices
- ❌ Expensive, central device failure = network down
- Most common (home & office networks)

### Bus Topology
- All devices share **one main cable (backbone)**
- ✅ Cheap, less cabling
- ❌ Slow, hard to troubleshoot
- ❌ Single cable failure breaks network

### Ring Topology
- Devices form a **loop**
- Data travels one direction
- ✅ Easy to find faults, less traffic
- ❌ One break = whole network fails
- Rare today

---

## Network Devices
### Router
- Connects **different networks**
- Uses **routing**
- Sends data across the Internet

### Switch
- Connects devices **inside the same network**
- Uses **packet switching**
- Breaks data into small packets
- Common in schools, offices

---

## Subnetting
- Splitting one network into **smaller networks**
- Improves:
  - Efficiency
  - Security
  - Control
- Uses a **subnet mask (32 bits, 0–255)**

### Important terms
- **Network address** → identifies network (ends in .0)
- **Host address** → identifies device
- **Default gateway** → router, way out of network

---

## ARP (Address Resolution Protocol)
- Matches **IP address ↔ MAC address**
- Uses:
  - **ARP Request** → “Who has this IP?”
  - **ARP Reply** → “I do”
- Stores results in **ARP cache**
- MAC = physical ID
- IP = logical ID (can change)

---

## DHCP
- Automatically gives devices IP addresses
- Steps:
  1. **DHCP Discover** – asking for IP
  2. **DHCP Offer** – server offers IP
  3. **DHCP Request** – device accepts
  4. **DHCP Acknowledge** – server confirms

---

## Key Answers Recap
- LAN = **Local Area Network**
- Router job = **Routing**
- Switch tech = **Packet Switching**
- Cost-efficient topology = **Bus**
- Expensive topology = **Star**
- Subnetting bits = **32**
- ARP stands for **Address Resolution Protocol**
- Physical ID = **MAC Address**
- Logical ID = **IP Address**
- DHCP first packet = **Discover**
- DHCP final packet = **Acknowledge**
