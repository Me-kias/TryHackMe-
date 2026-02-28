# Networking Core Protocols - TryHackMe Notes

## Task 1: Introduction
- This is the **third room** out of four about computer networking.  
- Recommended: complete **Networking Concepts** and **Networking Essentials** rooms first.  
- In this room, we learn about **additional protocols**.  
- Start your machine and attack box to follow along.

---

## Task 2: DNS (Domain Name System)
- DNS translates **domain names** (like `google.com`) into **IP addresses**.  
- Works on **Layer 7**.  
- Default ports: **UDP 53** (main) and **TCP 53** (fallback).  

### Common DNS Records:
| Record | Purpose |
|--------|---------|
| A      | Maps a hostname to an IPv4 address |
| AAAA   | Maps a hostname to an IPv6 address |
| CNAME  | Maps one domain to another domain |
| MX     | Specifies the mail server for a domain |

- Use `nslookup <domain>` to query DNS records.  
- Example: `nslookup example.com` gives A, AAAA, and other records.

- **IPv6 record** → `AAAA`  
- **Email server record** → `MX`  

---

## Task 3: WHOIS
- `whois <domain>` shows **domain registration info**.  
- Provides info like registrar, creation date, owner (sometimes company info).  
- Example:  
  ```bash


## Task 4: HTTP / HTTPS

- **HTTP** (Hypertext Transfer Protocol) is used to **transfer web pages** (HTML) from a server to a browser.  
- **HTTPS** is the **secure version**; it encrypts the data during transfer.  

### How it works:
1. Browser sends a **request** to the web server (e.g., `GET /` for the homepage).  
2. Server responds with a **status code** (e.g., `200 OK`) and **HTML content**.  
3. Browser renders the HTML as a web page.  

### Common HTTP Methods:
| Method | Purpose |
|--------|---------|
| GET    | Request data from a server |
| POST   | Send data to a server |
| PUT    | Update existing data |
| DELETE | Remove a resource |

### Ports:
- **HTTP:** TCP 80  
- **HTTPS:** TCP 443  

### Example using Telnet:
1. Connect to the server on port 80:
   ```bash
   telnet <IP> 80

  
  whois x.com
  whois twitter.com
  ## Task 5: FTP (File Transfer Protocol)

- **FTP** is used to **transfer files** between a client and a server.  
- Default port: **TCP 21**  

### Common FTP Commands:
| Command | Purpose |
|---------|---------|
| USER <username> | Login with a username |
| PASS <password> | Login with a password |
| LS      | List files on the server |
| GET <file> | Download a file from the server |
| PUT <file> | Upload a file to the server |
| QUIT    | Exit the FTP session |

### Example Workflow:
1. Connect to the FTP server:


   ## Task 6: SMTP (Simple Mail Transfer Protocol)

- **SMTP** is used to **send emails** from a client to a server or between servers.  
- Default port: **TCP 25**  

### Common SMTP Commands:
| Command | Purpose |
|---------|---------|
| HELO / EHLO | Start the connection with the server |
| MAIL FROM: | Specify the sender's email address |
| RCPT TO: | Specify the recipient's email address |
| DATA    | Start writing the email content |
| .       | End the email message |
| QUIT    | Close the connection |

### How it works:
1. Connect to the SMTP server (e.g., via Telnet):
  
   ## Task 7: POP3 (Post Office Protocol v3)

- **POP3** is used to **receive/download emails** from a mail server to a local client.  
- Default port: **TCP 110**  

### Common POP3 Commands:
| Command | Purpose |
|---------|---------|
| USER <username> | Login with the email username |
| PASS <password> | Provide the email password |
| STAT    | Show number of messages and mailbox size |
| LIST    | List all messages with their sizes |
| RETR <number> | Retrieve a specific message |
| DELE <number> | Delete a specific message |
| QUIT    | Exit the session |

### How it works:
1. Connect to the POP3 server:

   ## Task 8: IMAP (Internet Message Access Protocol)

- **IMAP** is used to **access and manage emails on a server** from multiple devices.  
- Unlike POP3, it **synchronizes messages** across all devices.  
- Default port: **TCP 143**  

### Common IMAP Commands:
| Command | Purpose |
|---------|---------|
| LOGIN <username> <password> | Login to the mailbox |
| SELECT <mailbox> | Choose which mailbox to access (e.g., INBOX) |
| FETCH <number> BODY | Retrieve the content of a specific message |
| MOVE <number> <folder> | Move a message to another folder |
| COPY <number> <folder> | Copy a message to another folder |
| LOGOUT | Exit the session |

### How it works:
1. Connect to the IMAP server:

   ## Task 9: Protocol Summary & Common Ports

- Knowing **default ports** and transport protocols is important for networking and cybersecurity.  
- Most protocols use **TCP**, except DNS which can use **UDP or TCP**.  
- There are **65,535 ports**, but only a small set are commonly used.  

### Common Protocols and Ports
| Protocol | Default Port | Transport | Purpose |
|----------|--------------|-----------|---------|
| DNS      | 53           | UDP/TCP   | Domain name resolution |
| HTTP     | 80           | TCP       | Web pages |
| HTTPS    | 443          | TCP       | Secure web pages |
| FTP      | 21           | TCP       | File transfer |
| SMTP     | 25           | TCP       | Sending email |
| POP3     | 110          | TCP       | Receiving email |
| IMAP     | 143          | TCP       | Accessing/syncing email |
| SSH      | 22           | TCP       | Secure remote access |
| Telnet   | 23           | TCP       | Remote access (insecure) |
| RDP      | 3389         | TCP       | Remote desktop |

### Notes:
- Memorize these **common ports** for exams like **CompTIA Network+, CEH, Pentest+**, or general networking tasks.  
- Only about **30 ports** are essential for most practical work.  
- Knowing **transport protocols** (TCP vs UDP) is also important for security and troubleshooting.  

**Tip:** Use this as a **cheat sheet** for quick reference when studying protocols and ports.
