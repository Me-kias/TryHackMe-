# TryHackMe — DNS in Detail (Notes)

These notes cover the **DNS in Detail**  
DNS helps computers find each other on the internet using names instead of numbers.

---

## Task 1: What is DNS?
- **DNS (Domain Name System)** turns website names into IP addresses.
- Computers use **IP addresses** (example: `192.168.1.1`) to communicate.
- IP addresses are hard to remember, so DNS lets us use names like `tryhackme.com`.

**Example:**  
Website name → DNS → IP address → Website loads

---

## Task 2: Domain Hierarchy
Domain names are read **from right to left**.

### Top-Level Domains (TLDs)
- The last part of a domain name.
- Two main types:
  - **gTLD (Generic TLD)**: `.com`, `.org`, `.edu`, `.gov`
  - **ccTLD (Country Code TLD)**: `.uk`, `.ca`, `.de`

### Second-Level Domain
- The main name of the website.
- Example: `tryhackme` in `tryhackme.com`
- Maximum length: **63 characters**
- Allowed characters: letters (`a–z`), numbers (`0–9`), and hyphens (`-`)
- Cannot start or end with a hyphen.

### Subdomains
- Added before the second-level domain.
- Example: `admin.tryhackme.com`
- Same rules as second-level domains.
- You can have **many subdomains**.
- The full domain name must be **under 253 characters**.
- **Underscores are not allowed**.

---

## Task 3: DNS Record Types
DNS uses records to store different types of information.

### A Record
- Links a domain name to an **IPv4 address**.

### AAAA Record
- Links a domain name to an **IPv6 address**.

### CNAME Record
- Points one domain name to another domain name.
- Example: a shop domain pointing to Shopify.
- DNS will then look up the second domain.

### MX Record
- Tells email servers where to send email.
- Includes a **priority number**.
- Lower number = higher priority.
- Used for backup email servers.

### TXT Record
- Stores text information.
- Common uses:
  - Email security (SPF, DKIM)
  - Domain ownership verification

---

## Task 4: How DNS Requests Work
When you visit a website:

1. Your computer checks its **local cache**.
2. If not found, it asks a **recursive DNS server** (usually from your ISP).
3. If still not found, the request goes to a **root DNS server**.
4. The root server points to the correct **TLD server**.
5. The TLD server points to the **authoritative DNS server**.
6. The authoritative server sends the DNS record back.
7. The answer is saved based on the **TTL (Time To Live)**.

### Important DNS Servers
- **Recursive DNS server**: Searches for the answer.
- **Root DNS server**: Directs traffic to the correct TLD.
- **TLD server**: Knows where authoritative servers are.
- **Authoritative DNS server**: Stores real DNS records.

### TTL (Time To Live)
- Measured in seconds.
- Controls how long DNS results are cached.
- Reduces DNS traffic and speeds up browsing.

---

## Task 5: Practical DNS Queries
- Used DNS tools to query records.
- Found:
  - CNAME record values
  - TXT record content
  - MX record priority number
  - A record IP address

This shows how DNS information can be discovered and analyzed.

---

## Summary
This room explains:
- How DNS works
- Domain name structure
- Common DNS record types
- The full DNS lookup process

DNS is a core concept for **networking**, **web security**, and **penetration testing**, especially when discovering websites, email systems, and attack surfaces.
