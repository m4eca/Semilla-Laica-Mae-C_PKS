## Overview

**Cross-Site Scripting (XSS)** is a type of web vulnerability that allows attackers to inject **malicious scripts** into trusted websites.  
When other users visit the affected page, the malicious script runs in their browser — often stealing cookies, session tokens, or personal information.

---

## How XSS Works

1. The attacker finds a **vulnerable input field** on a website (like a comment box or search bar).  
2. They inject a **script** (usually in JavaScript).  
3. When the page loads, the script executes on the browser of any user who views it.  
4. The attacker can now steal data, hijack sessions, or redirect users to fake pages.

---

## Types of XSS

### 1. **Stored XSS**
- The malicious script is **permanently saved** on the server (e.g., in a database or forum post).  
- Every time a user loads the infected page, the script automatically executes.

### 2. **Reflected XSS**
- The malicious script is part of a **URL or form input** and is immediately “reflected” back to the user by the server.  
- Common in search bars, login pages, or error messages.

### 3. **DOM-Based XSS**
- The attack happens entirely on the **client side** (browser).  
- The script manipulates the **Document Object Model (DOM)** directly without needing the server to respond.

---
## Prevention

- Always sanitize and validate user inputs before displaying them.
- Use HTML entity encoding (< becomes &lt;, > becomes &gt;).
- Implement Content Security Policy (CSP) to block unauthorized scripts.
- Avoid directly inserting untrusted data into HTML or JavaScript.
- Use frameworks or functions that automatically escape data (like React or Django templates).

## Real-World Impact

XSS can:

- Steal cookies, login sessions, and personal data.
- Change the appearance or content of websites.
- Redirect users to malicious sites.
-Perform phishing or trick users into giving away credentials.

---

## Reflection

This lesson showed how attackers can use simple things like comment boxes or search bars to run harmful scripts. I learned that there are different types of XSS, and each one works in its own way some save the script, some reflect it, and some run only in the browser. It’s important to clean and check user input properly, and use tools like CSP to help block these attacks before they happen.
