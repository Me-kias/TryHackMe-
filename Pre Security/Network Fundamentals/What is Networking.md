# Networking – Notes

- Networking = connecting things together  
- Example: friends connected by interests  

## In real life
- Transport systems  
- Power grid  
- Postal system  

## In computers
- Devices connect to communicate  
- Examples: phone, laptop, cameras, traffic lights  
- Can be small (2 devices) or very large (billions)

## Why it matters
- Used every day  
- Helps share data  
- Important for cybersecurity  

## Key term
- Devices connected together = **Network**

  
# What is the Internet?

- Internet = one **big network** made of many **small networks**
- Small networks connect together to form the Internet

## Simple example
- Alice connects two groups that speak different languages  
- Alice acts like the Internet, passing messages between them

## History
- First network: **ARPANET** (late 1960s)
- Funded by the **US Defence Department**
- **World Wide Web (WWW)** created in **1989**
- Invented by **Tim Berners-Lee**
- WWW made sharing information easy

## Network types
- **Private network** → small local networks  
- **Public network** → connects private networks (the Internet)

## Key answer
- **Who invented the World Wide Web?**  
  **Tim Berners-Lee** ✅

  # Identifying Devices on a Network (Notes)

## Why identification is needed
- Devices need IDs to know **who they are talking to**
- Like humans:
  - Name → can change
  - Fingerprints → cannot change

## Device identifiers
- **IP Address** → can change
- **MAC Address** → fixed (like a serial number)

---

## IP Address
- IP = **Internet Protocol**
- Used to identify a device on a network
- Made of **4 sections** called **octets**
- Example: `192.168.1.77`
- Only one device can use the same IP on a network at a time

### Types of IP addresses
- **Private IP** → used inside a local network
- **Public IP** → used on the Internet
- Public IPs are given by the **ISP**

### IPv4 vs IPv6
- **IPv4**: 4.3 billion addresses (running out)
- **IPv6**: very large number of addresses, more efficient

---

## MAC Address
- MAC = **Media Access Control**
- Physical address built into the device
- 12 hexadecimal characters
- Example: `a4:c3:f0:85:ac:2d`
- First half = manufacturer
- Second half = unique number

### MAC Spoofing
- MAC addresses can be **faked**
- Used to bypass weak security
- Common in public Wi-Fi (cafes, hotels)

---

## Key Answers
- IP stands for: **Internet Protocol**  
- Each part of an IP address: **Octet**  
- IPv4 sections: **4**  
- MAC stands for: **Media Access Control**

# Ping – Notes

## What is Ping?
- Ping is a basic network tool
- Checks if a device or website is **reachable**
- Measures **connection speed and reliability**

## How Ping Works
- Uses **ICMP** packets
- Sends an **echo request**
- Receives an **echo reply**
- Measures time in **milliseconds (ms)**

## Where Ping is Used
- Home networks
- Websites (e.g. Google)
- Works on **Windows** and **Linux**

## Ping Syntax
- `ping IP_address`
- `ping website_url`

## Example
- `ping 192.168.1.254`
- Shows packets sent, received, and response time

## Key Answers
- Protocol ping uses: **ICMP**
- Syntax to ping 10.10.10.10:  
  `ping 10.10.10.10`

