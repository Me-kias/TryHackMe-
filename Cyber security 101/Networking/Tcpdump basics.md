# TCPDump Basics – Task 1 (Intro)

## What is tcpdump?
- tcpdump is a **command-line tool** used to:
  - capture network packets
  - filter packets
  - analyze traffic

## Key idea
- It helps you see what’s happening on a network in real time or from saved files.

## Under the hood
- tcpdump is built on a library called:
  - **libpcap**

- On Windows, the equivalent is:
  - **WinPcap**

## Why it matters
- These libraries are the foundation for many network analysis tools (like Wireshark).

---

# TCPDump Basics – Task 2  (Basic Packet Capture)

## Network Interfaces
- A system can have multiple network interfaces such as:
  - loopback (`lo`)
  - ethernet (`eth0`, `ens5`)
  - wifi (`wlan0`)

### Find interfaces
```
ip a
```
or
```
ip address show
```

- This lists all interfaces and their IPs so you know what to capture from.

---

## Basic tcpdump Usage

### Capture traffic on a specific interface
```
tcpdump -i <interface>
```
- `-i` = interface selection
- Example: `tcpdump -i eth0`

### Capture on all interfaces
```
tcpdump -i any
```
- Captures traffic from all available interfaces

---

## Saving Packet Captures

### Write output to a file
```
tcpdump -w file.pcap
```
- Saves captured packets into a `.pcap` file for later analysis

---

## Reading Packet Captures

### Read from saved file
```
tcpdump -r file.pcap
```
- Displays packets from a previously saved capture

---

## Limiting Output

### Capture only a number of packets
```
tcpdump -c 10
```
- Stops capture after a set number of packets

---

## Output Formatting

### Show numeric output (no DNS lookup)
```
tcpdump -n
```
- Shows IP addresses only

### No DNS + no port name resolution
```
tcpdump -nn
```
- Shows raw IPs and port numbers only

---

## Verbose Mode

- `-v` → basic extra details
- `-vv` → more details
- `-vvv` → maximum detail

---
## Key Idea
- Always choose the correct interface before capturing
- Use `-n / -nn` to avoid messy name resolution
- Save captures when needed for later analysis
- Use `-c` to avoid overwhelming output

# TCPDump Basics – Task 3 Notes (Filtering Expressions)

## Why filtering is important
- tcpdump captures a LOT of traffic by default
- Filters help you:
  - reduce noise
  - focus on specific traffic
  - make analysis faster and easier

---

## Host-based filtering

### Filter by host (IP or domain)
```
host <ip-or-domain>
``` id="h3a1"

### Source only
```
src host <ip>
``` id="h3a2"

### Destination only
```
dst host <ip>
``` id="h3a3"

- Useful for isolating traffic from/to a single machine

---

## Port-based filtering

### Filter by port
```
port 53
``` id="p3a1"

### Source port
```
src port 80
``` id="p3a2"

### Destination port
```
dst port 443
``` id="p3a3"

- Common ports:
  - 53 → DNS
  - 80 → HTTP
  - 443 → HTTPS

---

## Protocol filtering

### Filter by protocol type
```
tcp
udp
icmp
``` id="pr3a1"

- Helps isolate traffic types quickly

---

## Logical operators

### AND (both conditions must match)
```
host 1.1.1.1 and tcp
``` id="lo3a1"

### OR (either condition matches)
```
udp or icmp
``` id="lo3a2"

### NOT (exclude traffic)
```
not tcp
``` id="lo3a3"

---

## Example use cases

- DNS traffic → `port 53`
- SSH traffic → `tcp port 22`
- Web traffic → `tcp port 80 or 443`
- Ping → `icmp`

---

## Key idea
- Filters can be combined for precision:
  - host + port + protocol
- Logical operators make filtering powerful

---


# TCPDump Basics – Task 4 Notes (Advanced Filtering)

## Overview
- Task 4 focuses on **more advanced tcpdump filters**
- These help you go beyond simple host/port/protocol filtering

---

## Packet size filtering

### Greater than a value
```
greater 1500
``` id="g8k2ap"

### Less than a value
```
less 100
``` id="d1q9mv"

- Useful for:
  - spotting large data transfers
  - identifying unusual packet sizes
  - filtering noise

---

## Understanding TCP flags

TCP packets include **flags** that describe connection state:

- SYN → start connection
- ACK → acknowledgment
- RST → reset connection
- FIN → finish connection
- PSH → push data

---

## Filtering by TCP flags

### Only SYN packets
```
tcp[tcpflags] == tcp-syn
``` id="s2m8vq"

### Only RST packets
```
tcp[tcpflags] == tcp-rst
``` id="k4n1jd"

- This means ONLY packets with that exact flag set

---

## Flag conditions (broader matching)

### At least SYN is present
```
tcp[tcpflags] & tcp-syn != 0
``` id="p7xq2k"

- Matches packets where SYN is set (may include others too)

### SYN or ACK
```
tcp[tcpflags] & (tcp-syn|tcp-ack) != 0
 id="v1m8zd"

- Matches packets that contain either SYN or ACK

---

## Key concepts

### Exact match vs partial match
- `==` → only that flag exists
- `& != 0` → flag is present (even with others)

---

## Practical uses

- Detect scans (SYN floods)
- Find resets (RST issues)
- Identify unusual traffic patterns
- Analyze connection setup/teardown

---

## Key takeaway
- Advanced filtering allows:
  - packet size analysis
  - TCP flag inspection
  - deeper network troubleshooting

# TCPDump Basics – Task 5 Notes (Displaying Packets)

## Overview
- After filtering packets, tcpdump allows you to control **how results are displayed**
- This helps make output easier to read or more detailed depending on the need

---

## Basic display options

### Quick summary output
```
tcpdump -q
``` id="q1n8ab"

- Shows minimal information
- Only essential packet details (fast view)

---

## Link-layer details

### Show MAC addresses
```
tcpdump -e
``` id="e9k2vx"

- Displays **link-layer (Ethernet) information**
- Useful for seeing:
  - source MAC address
  - destination MAC address

---

## ASCII output

### Show packet data in ASCII
```
tcpdump -A
``` id="a3m7cd"

- Converts packet payload into readable text
- Useful for:
  - spotting HTTP requests
  - reading readable strings in traffic

---

## Hex output

### Show packet data in hexadecimal
```
tcpdump -XX
``` id="x8p4lm"

- Displays:
  - hex dump
  - ASCII representation together

### Show only hex output (no ASCII mix)
```
tcpdump -X
``` id="x2v9qn"

- Used for deeper packet inspection
- Helps analyze raw packet structure

---

## Key differences

- `-q` → quick minimal view
- `-e` → shows MAC addresses (Layer 2 info)
- `-A` → readable text (ASCII payload)
- `-X` / `-XX` → raw packet data (hex + ASCII)

---

## When to use what

- Troubleshooting connections → `-q`
- Network layer analysis → `-e`
- Reading web traffic → `-A`
- Deep forensic analysis → `-X` or `-XX`

---

## Key takeaway
- Display options change **how packets are viewed, not what is captured**
- Combine with filters for best results

