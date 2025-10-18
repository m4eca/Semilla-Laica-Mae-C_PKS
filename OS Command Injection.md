## Definition

**OS Command Injection** is a web security vulnerability that allows an attacker to execute **arbitrary operating system commands** on the server running an application.  
This happens when an application takes **untrusted input** and passes it directly to a system command without proper validation or sanitization.

---

## How It Works

1. The web application receives input from a user (for example, through a form or URL parameter).  
2. The input is used inside a system command such as `ping`, `cat`, or `ls`.  
3. If the application does not filter or sanitize the input, an attacker can inject additional commands.  
4. The server executes the injected commands with the same privileges as the web application.

**Example (Vulnerable Code in PHP):**
```php
<?php
  $ip = $_GET['ip'];
  system("ping -c 4 " . $ip);
?>
```

If the attacker enters:
```bash
127.0.0.1; ls
```

The server will execute:
```ngixx
ping -c 4 127.0.0.1; ls
```
This allows the attacker to list files on the server.


---
## Potential Impact
- Unauthorized access to the operating system.
- Data exposure, modification, or deletion.
- Gaining full control of the web server.
- Using the compromised server as a pivot point for further attacks.

## Common Injection Points
- Form fields (search bars, login inputs, etc.)
- URL query parameters
- HTTP headers (User-Agent, Cookie)
- File uploads or system call functions

## Prevention Techniques
- Input Validation: Allow only safe and expected input values. 
- Input Sanitization: Remove or escape special characters such as ;, |, &, >, <. 
- Use Safe APIs: Avoid using system-level functions like exec() or system() when possible. 
- Least Privilege: Run applications with limited permissions to reduce damage if exploited.
- Output Encoding: Encode data before displaying it to prevent command injection through responses.
