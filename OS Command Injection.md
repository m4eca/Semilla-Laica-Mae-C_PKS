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
