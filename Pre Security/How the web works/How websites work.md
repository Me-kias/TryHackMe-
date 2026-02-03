# TryHackMe – How Websites Work (Complete Notes)

## Task 1: How Websites Work

- When you visit a website, your **browser** (Chrome, Firefox, Safari, etc.) sends a **request** to a **web server**
- A **web server** is just a computer somewhere else that responds to requests
- The server sends back:
  - Website content (HTML, CSS, JS)
  - Or an error code if something fails

### Request / Response flow
Browser → Internet → Web Server → Internet → Browser

- Common response code: `200 OK`
- Browser **renders** the response into a page you can see

### Website components
- **Front-end (client-side)**
  - What the browser renders
  - What the user sees

- **Back-end (server-side)**
  - Handles logic and processing
  - Sends responses

Key idea: websites work in a **back-and-forth request/response cycle**.

---

## Task 2: HTML

Websites are mainly built with:
- **HTML** → structure
- **CSS** → styling
- **JavaScript** → interactivity

### HTML basics
- HTML = HyperText Markup Language
- Built using **elements (tags)**
- Tags tell the browser how to display content

### Core structure
- `<!DOCTYPE html>` → declares HTML5
- `<html>` → root element (wraps everything)
- `<head>` → page info (title, metadata)
- `<body>` → visible content

### Common tags
- `<h1>` to `<h6>` → headings
- `<p>` → paragraph text
- `<img>` → images
- `<button>` → buttons
- Lists, links, etc.

### Attributes
- `class`
  - Used for styling
  - Can be reused

- `id`
  - Must be **unique**
  - Used by CSS and JavaScript

- `src`
  - File location (mostly images)

## Task 3: JavaScript

- JavaScript (JS) is one of the most popular programming languages
- It makes websites **interactive**
- Without JavaScript, web pages would be **static** (no dynamic behavior)

### What JavaScript is used for
- Dynamically updating page content
- Responding to user actions (clicks, hover, etc.)
- Changing styles or elements in real time
- Adding animations and interactive features

HTML = structure  
JavaScript = functionality

---

### How JavaScript is added to a webpage

JavaScript can be:
- Written directly inside the HTML using `<script>` tags
- Loaded from an external file using the `src` attribute

## Task 4: Sensitive Data Exposure

### What is Sensitive Data Exposure?
Sensitive Data Exposure happens when a website:
- Doesn’t properly protect sensitive information
- Leaves sensitive data visible in **front-end code**

This data is often exposed by mistake.

---

### Where sensitive data is commonly found
- HTML source code
- JavaScript files
- HTML comments
- Hidden links or fields

You can see all of this by:
- Right‑clicking a page
- Clicking **View Page Source**

---

### Examples of exposed sensitive data
- Usernames and passwords
- API keys
- Temporary credentials
- Admin or hidden URLs

## Task 5: HTML Injection

### What is HTML Injection?
HTML Injection is a vulnerability that happens when:
- User input is **not sanitized**
- That input is displayed directly on the page
- The browser treats the input as real HTML

This allows attackers to inject their own HTML (and sometimes JavaScript).

---

### Why HTML Injection is dangerous
If an attacker can control what gets displayed, they can:
- Change page content
- Inject malicious links
- Alter how the page looks or behaves
- Potentially escalate to XSS

If users can add code to a page → **very bad**

---

### How HTML Injection happens
1. User enters input into a form
2. Input is passed to a JavaScript function
3. Output is written directly to the page
4. No filtering or validation is applied

Result: injected HTML is rendered by the browser

---

### Example vulnerable behavior
- Input field asks: “What’s your name?”
- Whatever is entered is reflected back on the page
- No sanitization is done

This means HTML tags will run instead of being treated as text.

---

### Golden rule
**Never trust user input**

Even if you think users are harmless:
- Sanitize all input
- Remove or escape HTML tags
- Validate input before using it

If input is not sanitized, you **will** have a bad day.

---

### Hands-on Task

Inject a malicious HTML link into the input field:

```html
<a href="http://hacker.com">Hacker site</a>

