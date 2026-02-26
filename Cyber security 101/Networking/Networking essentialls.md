# 🧠 Networking Essentials — Human Notes (Practical Understanding)



---

# 1) DHCP — “Hey network, who am I?”

Whenever you connect to a new WiFi (home → cafe → school), your device needs:

- IP address → your identity
- Default Gateway → exit door to internet
- DNS server → internet phonebook

Instead of setting manually, **DHCP does everything automatically.**

## How it works (DORA process)

Think of entering a new office and asking for an ID card.

| Step | What device says | What it means |
|----|----|----|
| Discover | Anyone giving IP addresses? | Broadcast request |
| Offer | Take this IP | Server offers configuration |
| Request | I accept it | Device confirms |
| Acknowledge | Done, it's yours | Server finalizes |

### Important facts
- Source IP = `0.0.0.0` → you don’t have identity yet
- Destination IP = `255.255.255.255` → ask everyone
- Total steps = **4**

After this → internet works.

---

# 2) ARP — “I know your IP, but where are you physically?”

Computers **do NOT send data using IP addresses internally**
They send using **MAC addresses (hardware address)**

So the system must translate:

```
IP → MAC
```

## What happens

Your PC wants to talk to `192.168.1.10`

It broadcasts:

> WHO HAS 192.168.1.10 ?

All devices receive it.

Correct device replies:

> I HAVE IT → MY MAC IS AA:BB:CC:DD:EE:FF

Your PC saves it inside **ARP Cache** (memory table)

Now communication becomes fast.

### Key points
- ARP Request → Broadcast
- ARP Reply → Direct response
- Maps IP to MAC
- Works between Layer 2 and 3

---

# 3) ICMP — “Are you alive?”

Used for **testing connectivity**, not sending normal data.

---

## Ping

Just checks:

> Can I reach you?

Send echo → receive echo reply

If reply comes → host is reachable

Important:
- Ping sends small data packet (echo request)
- Target copies it back (echo reply)

---

## Traceroute

Shows the **path your packet takes across routers**

Packets contain a value called:

```
TTL = Time To Live
```

Each router reduces TTL by 1

When TTL becomes 0:
Router drops packet and replies:
> Time exceeded

So traceroute sends multiple packets:

TTL 1 → first router replies  
TTL 2 → second router replies  
TTL 3 → third router replies  

Finally → destination replies

You now see full route to server.

---

# 4) Routing — How internet finds the way

Internet has millions of possible paths.

Routers use routing protocols to choose best path.

You don’t need deep details, just remember:

| Protocol | Purpose |
|----|----|
| OSPF | Finds shortest path inside network |
| EIGRP | Cisco proprietary routing |
| RIP | Small/simple networks |
| BGP | Internet’s main routing protocol |

👉 **BGP runs the internet**

---

# 5) NAT — One house, one public address

Problem:
We don’t have enough public IP addresses for every device.

Solution:
Router uses **NAT (Network Address Translation)**

## What actually happens

Inside your home:

| Device | Private IP |
|----|----|
| Laptop | 192.168.1.2 |
| Phone | 192.168.1.3 |
| TV | 192.168.1.4 |

Outside internet sees:

```
All devices = ONE public IP
```

Router keeps a translation table:

```
192.168.1.2:53421 → 8.34.21.9:40001
192.168.1.3:53422 → 8.34.21.9:40002
```

So replies come back to correct device.

### Key concept
Ports allow **~65,000 simultaneous connections**

---

# 6) Quick Memory Cheat Sheet

| Task | Protocol |
|----|----|
| Get IP automatically | DHCP |
| Find MAC from IP | ARP |
| Check connectivity | ICMP (ping) |
| Find path to host | Traceroute |
| Route across internet | BGP |
| Share one public IP | NAT |

---

# Mental Model (Remember This)

Joining WiFi:

1. DHCP → get identity
2. ARP → find neighbor hardware
3. ICMP → test reachability
4. Routing → choose path
5. NAT → exit to internet

That’s literally how internet works.
