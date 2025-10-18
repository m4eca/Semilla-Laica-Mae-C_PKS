
## **Definition**  
OS Command Injection is a type of vulnerability where an attacker manipulates input to execute arbitrary system-level commands via a vulnerable application. This typically happens when user input is passed directly to a shell or command interpreter without proper validation.

---

## **Impact**  
- Grants attackers **remote control** over the target system  
- If the application runs with **admin/root privileges**, injected commands inherit those privileges  
- Can compromise systems even when attackers lack direct OS access (e.g., via web apps)
  
---

## **Risk Factors**  
- Applications that **concatenate user input into shell commands**  
- Use of **special shell characters** like `&`, `&&`, `|`, `||`, `;`  
- Lack of input sanitization or escaping mechanisms
  
---

## **Prevention Strategies**  
- **Avoid shell execution**: Use safer APIs that don’t invoke the shell (e.g., parameterized functions)  
- **Sanitize input**: Filter out or escape dangerous characters  
- **Validate input**: Accept only expected formats (e.g., numbers, filenames)  
- **Use least privilege**: Run applications with minimal required permissions  
- **Security libraries**: Employ frameworks or tools that handle command execution securely
  
---
