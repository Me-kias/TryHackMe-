# TryHackMe – Putting It All Together (Notes)

## Video Overview
This room ties together everything learned so far and shows how all the web components work together when you visit a website.

---

## Task 1: Putting It All Together

When you request a website in your browser, a lot happens behind the scenes.

### High-level flow
1. Your computer needs to know the **IP address** of the website
2. It uses **DNS (Domain Name System)** to find it
3. Your browser talks to the web server using **HTTP**
4. The web server responds with:
   - HTML
   - CSS
   - JavaScript
   - Images, videos, etc.
5. Your browser formats and displays the website

### Simple view
Browser → DNS → Web Server → Browser → Website displayed

Other components also help make websites:
- Faster
- More reliable
- More secure

---

## Task 2: Other Components

### Load Balancers
Used when:
- A site has lots of traffic
- High availability is required

What they do:
- Distribute traffic across multiple servers
- Provide **failover** if one server goes down

How they work:
- Receive the request first
- Forward it to a backend server

Common algorithms:
- **Round robin** → sends requests evenly
- **Weighted** → sends traffic to the least busy server

Health checks:
- Load balancers constantly check if servers are alive
- Called **health checks** or **heartbeats**
- If a server fails, traffic stops going to it

---

### CDNs (Content Delivery Networks)

What a CDN does:
- Hosts **static files** like:
  - Images
  - CSS
  - JavaScript
  - Videos

Why they’re useful:
- Reduce load on main servers
- Speed up websites
- Serve content from the closest location to the user

How it works:
- CDN finds the nearest server to the user
- Sends content from there instead of far away

Example:
- Amazon CloudFront
- Netflix uses CDNs to stream faster

---

### Databases

Why websites use databases:
- Store user data
- Store posts, comments, credentials, etc.

Database types:
- Simple text files
- Large clustered systems

Common databases:
- MySQL
- Microsoft SQL
- MongoDB
- PostgreSQL
- GraphQL

Each database is designed for different use cases.

---

### WAFs (Web Application Firewalls)

What a WAF does:
- Sits between the user and the web server
- Protects against:
  - Attacks
  - Bots
  - Denial of Service (DoS)

What it checks:
- Common attack patterns
- If traffic is from a real browser
- Request rate (rate limiting)

Example:
- Cloudflare

If a request looks malicious:
- It gets dropped
- Never reaches the web server

---

### Task 2 Questions
- What hosts static files and speeds up websites? → **CDN**
- What checks if a server is alive? → **Health check**
- What helps protect against web attacks? → **WAF**

---

## Task 3: How Web Servers Work

### What is a web server?
A web server is software that:
- Listens for incoming connections
- Uses HTTP to deliver content

Common web servers:
- Apache
- Nginx
- IIS (Microsoft)
- Node.js

---

### Web server root directories

Where files are served from:

Linux (Apache / Nginx):
```text
/var/www/html
