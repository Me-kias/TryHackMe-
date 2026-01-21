# TryHackMe — Extending Your Network (Notes)

Focus areas: port forwarding, firewalls, VPNs, and core networking devices.

---

## Task 1: Port Forwarding
- **Port forwarding** allows services inside a private network (e.g. web server on port 80) to be accessible from the internet.
- Without it, services are only available internally (intranet).
- The **router** forwards traffic from a public IP and port to an internal IP and port.
- Port forwarding opens ports; **firewalls decide** whether traffic is allowed through those ports.

**Key takeaway:** Port forwarding is configured on a **router**.

---

## Task 2: Firewalls 101
- A **firewall** controls what traffic can enter or leave a network.
- Rules are based on:
  - Source & destination IP
  - Source & destination port
  - Protocol (TCP/UDP)

### Firewall Types
**Stateful**
- Tracks the entire connection.
- More secure, more resource-intensive.
- Can block a device based on connection behavior.

**Stateless**
- Inspects individual packets only.
- Faster and lightweight.
- Effective for high-volume traffic (e.g. DDoS).

**OSI Layers:** Firewalls commonly operate at **Layer 3 (Network)** and **Layer 4 (Transport)**.

---

## Task 3: Practical – Firewall
- Identified malicious traffic by **source IP**.
- Created a firewall rule to **drop traffic** from attacker to destination port 80.
- Rules typically define:
  - Source
  - Destination
  - Port
  - Action (allow/deny/drop)

---

## Task 4: VPN Basics
- A **VPN (Virtual Private Network)** creates an encrypted tunnel between devices or networks.
- Used to securely connect remote devices or entire networks.
- TryHackMe uses a VPN to safely access vulnerable machines.

### Benefits
- Secure communication
- Privacy & encryption
- Network-to-network connectivity

### VPN Technologies
- **PPP**: Authentication and encryption only (non-routable).
- **PPTP**: Easy to set up, weak encryption.
- **IPSec**: Strong encryption, harder to configure, widely supported.

---

## Task 5: LAN Networking Devices
### Router
- Connects **different networks**.
- Operates at **OSI Layer 3**.
- Handles routing, port forwarding, and firewall rules.

### Switch
- Connects devices within the **same network**.
- **Layer 2 switch**: Forwards frames using MAC addresses.
- **Layer 3 switch**: Can also route packets using IP addresses.

### VLANs
- Virtually segment a network for **security and isolation**.
- Devices can share internet access but be restricted from communicating with each other.

---

## Task 6: Practical – Network Simulator
- Simulated TCP traffic between hosts.
- Observed the **TCP three-way handshake** in the network log.
- Packet flow clearly shows connection setup, acknowledgment, and data transfer.

---

## Summary
This room covers how networks are extended securely using:
- Port forwarding
- Firewalls (stateful vs stateless)
- VPN technologies
- Routers, switches, and VLANs

A strong foundation for understanding real-world network exposure and defense.
