# HTTP in Detail — TryHackMe (Human Notes)

## Overview
This room explains how a browser communicates with a web server using **HTTP**.  
This knowledge is fundamental for:
- Web hacking
- CTFs
- Pentesting
- Understanding tools like Burp Suite

---

## Task 1: What is HTTP(S)?

### HTTP
- **HTTP** = HyperText Transfer Protocol
- Used whenever you visit a website
- Created by **Tim Berners-Lee** (1989–1991)
- A set of rules for communicating with web servers
- Used to transfer:
  - HTML
  - Images
  - Videos
  - Other web content

### HTTPS
- Secure version of HTTP
- Data is **encrypted**
- Prevents:
  - People reading your traffic
  - Data being modified
  - Talking to fake / impersonated servers
- Uses certificates and signatures to verify server identity

**Key answers**
- HTTP stands for: **HyperText Transfer Protocol**
- The `S` in HTTPS stands for: **Secure**

---

## Task 2: Requests and Responses

### What is a URL?
- **URL** = Uniform Resource Locator
- A set of instructions that tells your browser **how and where** to access a resource

### URL structure

### URL parts (important)
- **Scheme** → protocol (`http`, `https`, `ftp`)
- **User:Password** → optional authentication
- **Host** → domain name or IP address
- **Port**
  - HTTP → 80
  - HTTPS → 443
  - Common alternative → 8080
- **Path** → resource location on the server
- **Query string** → extra info (`?id=1`)
- **Fragment** → jump to a section of a page

> The **most important parts to remember** are the **host** and the **path**.

---

### Making an HTTP request

A request can be as simple as:

#### Breakdown
- **GET** → request method
- **/** → resource being requested
- **HTTP/1.1** → protocol version
- Requests end with a **blank line**

### Headers
- Headers send **extra information** to the server
- Used to give a richer web experience
- Example headers:
  - `Host`
  - `User-Agent`
  - `Referer`

---

### HTTP Response

Example response line:

#### Response structure
1. Status line (version + status code)
2. Headers
3. Blank line
4. Response body (actual content)

#### Important response headers
- **Content-Type** → what kind of data is being sent
- **Content-Length** → how much data to expect
- **Server** → server software (not always shown)

**Key answers**
- HTTP version used: **HTTP/1.1**
- Header that tells browser how much data to expect: **Content-Length**

---

## Task 3: HTTP Methods

HTTP methods describe the **intended action** of a request.

### Common methods
- **GET**
  - Retrieve information
  - View pages
- **POST**
  - Send data
  - Create new records (login, signup)
- **PUT**
  - Update existing data
- **DELETE**
  - Remove data or records

### Examples
| Action | Method |
|------|--------|
| Create new user | POST |
| Update email | PUT |
| Delete uploaded image | DELETE |
| View article | GET |

> In practice, **GET** and **POST** are the most common.

---

## Task 4: HTTP Response Codes

Status codes tell the client **what happened** to the request.

### Status code ranges
- **100s** → informational (rare)
- **200s** → success
- **300s** → redirects
- **400s** → client errors (your fault)
- **500s** → server errors (interesting for hacking)

### Common status codes
- **200 OK** → request successful
- **201 Created** → new resource created
- **301** → permanent redirect
- **302** → temporary redirect
- **400 Bad Request** → malformed request
- **401 Unauthorized** → login required
- **403 Forbidden** → no permission
- **405 Method Not Allowed**
- **404 Not Found**
- **500 Internal Server Error**
- **503 Service Unavailable**

### Exam-style answers
- New user or blog created → **201**
- Page doesn’t exist → **404**
- Server crashes / DB down → **503**
- Editing profile without login → **401**

---

## Task 5: Headers

Headers are **extra bits of data** sent with requests and responses.

### Common request headers
- **Host**
  - Tells server which website you want
- **User-Agent**
  - Browser name and version
- **Content-Length**
  - Size of request data
- **Accept-Encoding**
  - Supported compression formats
- **Cookie**
  - Sends stored session data

### Common response headers
- **Set-Cookie**
  - Stores a cookie in the browser
- **Cache-Control**
  - How long data should be cached
- **Content-Type**
  - Type of data returned
- **Content-Encoding**
  - Compression used

**Key answers**
- Browser info header → **User-Agent**
- Data type header → **Content-Type**
- Website being requested → **Host**

---

## Task 6: Cookies

### What are cookies?
- Small pieces of data stored in the browser
- Saved using the **Set-Cookie** header
- Sent back to the server with every request

### Why cookies exist
- HTTP is **stateless**
- Cookies allow the server to:
  - Remember who you are
  - Keep you logged in
  - Store preferences

### Authentication flow
1. User logs in
2. Server verifies credentials
3. Server sends `Set-Cookie`
4. Browser stores cookie
5. Cookie is sent with future requests
6. Server recognizes the user

### Cookie details
- Cookie values are usually **tokens**, not plaintext passwords
- Tokens are hard to guess and act as session identifiers

### Viewing cookies
- Open **Developer Tools**
- Go to **Network** tab
- Click a request
- View cookies under the **Cookies** tab

**Key answer**
- Header used to save cookies → **Set-Cookie**

---

## Task 7: Making Requests

An HTTP request emulator is used to practice requests.

### Completed actions
- `GET /room`
- `GET /blog?id=1`
- `DELETE /user/1`
- `PUT /user/2` with `username=admin`
- `POST /login`
  - username: `thm`
  - password: `letmein`

Each successful request returned a **flag**.

---

## Final Takeaways
- HTTP fundamentals are **critical** for web hacking
- You must understand:
  - Requests & responses
  - Methods
  - Status codes
  - Headers
  - Cookies
- This knowledge directly applies to:
  - Burp Suite
  - CTF challenges
  - Real-world pentesting

