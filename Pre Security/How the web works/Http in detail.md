# HTTP in Detail — TryHackMe Notes

## Video Overview
This room explains how web browsers communicate with web servers using the HTTP protocol, including:
- HTTP vs HTTPS
- Requests & responses
- URLs
- HTTP methods
- Status codes
- Headers
- Cookies
- Making HTTP requests

---

## Task 1: What is HTTP(S)?

### HTTP
- **HTTP** stands for **HyperText Transfer Protocol**
- Used whenever you view a website
- Developed by **Tim Berners-Lee** (1989–1991)
- A set of rules for communicating with web servers
- Transfers:
  - HTML
  - Images
  - Videos
  - Other web content

### HTTPS
- Secure version of HTTP
- Data is **encrypted**
- Prevents:
  - Data interception
  - Data modification
  - Server impersonation
- Uses certificates to verify server identity

### Key Points
- `HTTP` → Not secure
- `HTTPS` → Secure & encrypted

---

## Task 2: Requests and Responses

### What is a URL?
- **URL** = **Uniform Resource Locator**
- Instructions on how to access a resource on the internet

### URL Structure
