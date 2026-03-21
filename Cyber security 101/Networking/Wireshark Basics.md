# 🦈 Wireshark Basics (TryHackMe) – Notes

## Task 1 – Intro
- Wireshark = packet analyzer tool  
- Captures network traffic → saves as `.pcap` (packet capture files)
- Used to inspect and analyze network activity

**Recommended knowledge:**
- Basic networking
- OSI model

👉 Use the `exercise.pcap` file (not demo)

---

## Task 2 – Tool Overview

### Why use Wireshark?
- Troubleshooting networks
- Security analysis (SOC, pentesting, forensics)
- Detect anomalies

⚠️ Not an IDS (Intrusion Detection System)
- IDS = automatic alerts
- Wireshark = manual analysis

---

### Interface Overview
- **Toolbar** → start/stop capture
- **Display Filter Bar** → filter traffic (important)
- **Packet List Pane** → all packets
- **Packet Details Pane** → packet breakdown
- **Packet Bytes Pane** → raw hex + ASCII
- **Status Bar** → packet stats

---

### Opening a PCAP
- File → Open → select `.pcap`
- Click packets to inspect details

---

### Key Features
- Coloring rules → highlight protocols
- Capture traffic → choose interface
- Merge PCAPs → File → Merge
- File details → Stats → Capture File Properties

---

### Important Info (File Properties)
- Total packets
- Hash values (SHA256)
- Comments (may contain flags)

---

## Task 3 – Packet Dissection

### Packet Layers (OSI Model)

1. **Frame**
   - Size, timing info

2. **Layer 2 (Ethernet)**
   - MAC addresses

3. **Layer 3 (IP)**
   - IP addresses
   - TTL (time to live)

4. **Layer 4 (TCP/UDP)**
   - Ports
   - Sequence numbers
   - Flags (ACK, SYN)

5. **Application Layer**
   - Protocols (HTTP, DNS)

6. **Application Data**
   - Actual content (HTML, text)

---

### What to Look For
- TTL → IP layer
- Payload size → TCP section
- Headers → HTTP
- Data → Application section

---

## Task 4 – Packet Navigation

### Navigate
- Go to packet → `Ctrl + G`
- Search → `Ctrl + F`

Search in:
- Packet details (most useful)
- Packet bytes
- Packet list

---

### Marking
- Right-click → Mark packet
- Right-click → Add comment

---

### Exporting

#### Export Packets
- File → Export Specified Packets

#### Export Objects
- File → Export Objects → HTTP
- Extract files (images, txt, etc.)

---

### Extract File Example
- Find packet with file
- Right-click → Export Packet Bytes
- Save locally

---

### MD5 Hash
```bash
md5sum filename
```

- Used to verify file integrity

---

### Expert Info
- Shows:
  - Errors
  - Warnings
  - Notes

Access:
- Bottom icon OR Analyze → Expert Info

---

## Task 5 – Packet Filtering

### Types
1. Capture filter → before capture
2. Display filter → after capture (used most)

---

### Apply Filters
- Right-click → Apply as Filter

Examples:
- Filter by IP
- Filter by port
- Filter by protocol

---

### Conversation Filters
- Shows full communication between devices

---

### Colorize Traffic
- Right-click → Colorize conversation

Reset:
- View → Colorize → Reset

---

### Build Filters
- Right-click → Prepare as Filter
- Combine multiple filters before applying

---

### Add Columns
- Right-click field → Apply as Column

---

### Follow Streams (IMPORTANT)
- Right-click → Follow → TCP/HTTP Stream

Shows full readable conversation

Useful for:
- Extracting data
- Viewing requests/responses

---

## Key Skills Learned
- Analyze PCAP files
- Understand packet layers
- Filter traffic
- Extract files
- Use hashes
- Follow streams

---

## Final Notes
- Wireshark is powerful
- Filtering is the most important skill
- Practice = improvement
