# OWASP Top 10 (2021)

### A01:2021 - Broken Access Control
- **Description:** Occurs when an application fails to enforce what authenticated (or unauthenticated) users are allowed to do. Users can access functions or data outside their permissions.
- **Example:** IDOR — changing `id=12345` to `id=67890` to view or modify another user's records.
- **Impact:** Data exposure, privilege escalation, unauthorized actions.
- **Mitigation (short):** Enforce server-side authorization checks, deny-by-default, and test role boundaries.

---

### A02:2021 - Cryptographic Failures
- **Description:** Sensitive data is not properly protected in transit or at rest due to weak or missing cryptography, poor key management, or use of deprecated algorithms.
- **Example:** Storing passwords with MD5 or sending sensitive fields over HTTP.
- **Impact:** Data theft, credential compromise, regulatory issues.
- **Mitigation (short):** Use strong, modern algorithms (TLS 1.2+), proper key management, and PBKDF2/BCrypt/Argon2 for passwords.

---

### A03:2021 - Injection
- **Description:** Occurs when untrusted input is sent to an interpreter (SQL, OS, LDAP, etc.) and executed as code or commands.
- **Example:** SQL Injection or OS Command Injection via unsanitized input.
- **Impact:** Data loss, data leakage, remote code execution, full takeover.
- **Mitigation (short):** Use parameterized queries/prepared statements, input validation, and least privilege for DB accounts.

---

### A04:2021 - Insecure Design
- **Description:** Weaknesses rooted in design and architecture (threat modeling and secure design absent), not just implementation bugs.
- **Example:** Password-reset flows that rely on easily-guessable personal info instead of time-limited tokens.
- **Impact:** Wide-reaching vulnerabilities that are costly to fix and can affect many users.
- **Mitigation (short):** Adopt threat modeling, secure-by-design practices, and design reviews early in the project lifecycle.

---

### A05:2021 - Security Misconfiguration
- **Description:** Default settings, incomplete configurations, or exposed admin interfaces that leave systems insecure.
- **Example:** Default credentials left unchanged, directory listing enabled, or unneeded features enabled in production.
- **Impact:** Easy takeover, data exposure, and increased attack surface.
- **Mitigation (short):** Harden configurations, remove defaults, automate secure deployments, and scan for misconfigurations.

---

### A06:2021 - Vulnerable and Outdated Components
- **Description:** Using libraries, frameworks, or modules with known vulnerabilities or failing to apply security updates.
- **Example:** Running an app with an outdated library that has an RCE vulnerability.
- **Impact:** Attackers exploit known bugs to compromise systems or escalate privileges.
- **Mitigation (short):** Keep dependencies updated, use SBOMs, subscribe to security advisories, and minimize third-party code.

---

### A07:2021 - Identification and Authentication Failures
- **Description:** Weaknesses in authentication, session management, or identity functions (e.g., weak passwords, missing MFA, session fixation).
- **Example:** No rate limiting on login forms (enables brute-force), or predictable session IDs.
- **Impact:** Account takeover, impersonation, unauthorized access.
- **Mitigation (short):** Implement MFA, strong password policies, secure session handling, and rate limiting.

---

### A08:2021 - Software and Data Integrity Failures
- **Description:** Assumptions that software updates, CI/CD pipelines, or critical data are trustworthy when they may be tampered with (supply chain risks).
- **Example:** Automatically executing unsigned updates or pulling unverified packages in build pipelines.
- **Impact:** Supply-chain compromise, backdoored releases, large-scale compromise.
- **Mitigation (short):** Verify integrity with signatures, secure build pipelines, and restrict auto-update behavior.

---

### A09:2021 - Security Logging and Monitoring Failures
- **Description:** Insufficient logging, alerting, or monitoring prevents timely detection and response to incidents.
- **Example:** Missing logs for authentication failures or disabled alerting for anomalous behavior.
- **Impact:** Delayed breach detection, extended attacker dwell time, failed investigations.
- **Mitigation (short):** Centralize logs, monitor critical events, create alerts, and test incident response procedures.

---

### A10:2021 - Server-Side Request Forgery (SSRF)
- **Description:** The application fetches a remote resource based on user input, and attackers can force requests to internal-only services or metadata endpoints.
- **Example:** Submitting a URL like `http://localhost:5000/admin` or AWS metadata endpoint to access internal data.
- **Impact:** Internal network scanning, data exposure, cloud credential theft.
- **Mitigation (short):** Validate and whitelist allowed URLs, block internal IP ranges, and restrict server-side outgoing requests.

---
