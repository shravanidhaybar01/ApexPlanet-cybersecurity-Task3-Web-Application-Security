Apex Planet – Web Application Security

Internship Task: Web Application Security

Organization: Apex Planet Software Pvt. Ltd.
Intern: Shravani Dhaybar
Domain: Cybersecurity
Task: Web Application Security
Platform: Kali Linux
Application: Damn Vulnerable Web Application (DVWA)

---

1. Project Overview

This project focuses on identifying and understanding common web application vulnerabilities through practical security testing in a controlled local laboratory environment.

The objective is to understand how vulnerabilities can be exploited and how appropriate security measures can prevent them.

2. Objectives

- Identify common OWASP web application vulnerabilities.
- Perform SQL Injection testing.
- Demonstrate Stored and Reflected Cross-Site Scripting.
- Understand Cross-Site Request Forgery.
- Test Local and Remote File Inclusion.
- Intercept and modify HTTP requests using Burp Suite.
- Perform controlled fuzzing using Burp Intruder.
- Analyze and configure HTTP security headers.
- Implement and document mitigation techniques.

3. Tools and Technologies

Tool| Purpose
Kali Linux| Security testing environment
DVWA| Vulnerable web application
Burp Suite| HTTP interception and testing
Apache| Web server
MariaDB/MySQL| Database
PHP| Server-side scripting
Firefox| Web browser
curl| HTTP header verification

4. Practical Tasks

Task 1: SQL Injection

Objective: Identify SQL Injection vulnerabilities and understand database information exposure.

Activities:

- Tested vulnerable SQL input fields in DVWA.
- Examined SQL query manipulation.
- Studied database information disclosure.
- Demonstrated prevention using prepared statements.

Mitigation:

- Use parameterized queries.
- Implement prepared statements.
- Validate user input.
- Apply least-privilege database permissions.

Task 2: Cross-Site Scripting (XSS)

Objective: Identify Stored XSS and Reflected XSS vulnerabilities.

Activities:

- Tested Stored XSS in DVWA.
- Tested Reflected XSS using query parameters.
- Observed JavaScript execution in the vulnerable application.
- Studied secure output encoding and CSP.

Mitigation:

- Apply context-aware output encoding.
- Use htmlspecialchars() in PHP.
- Validate untrusted input.
- Configure Content Security Policy.
- Use secure cookie settings.

Task 3: Cross-Site Request Forgery (CSRF)

Objective: Understand how unauthorized requests can change user account information.

Activities:

- Examined the DVWA password-change functionality.
- Inspected HTTP requests.
- Studied CSRF attack scenarios.
- Demonstrated token-based protection.

Mitigation:

- Implement unpredictable CSRF tokens.
- Validate tokens on the server.
- Use SameSite cookie attributes.
- Validate Origin/Referer where appropriate.
- Protect all state-changing operations.

Task 4: File Inclusion

Objective: Understand Local File Inclusion and Remote File Inclusion vulnerabilities.

Activities:

- Tested file inclusion functionality in DVWA.
- Studied local file path traversal.
- Examined remote file inclusion risks.
- Reviewed PHP configuration and secure file handling.

Mitigation:

- Use file allowlisting.
- Avoid directly using user input in file paths.
- Disable remote file inclusion.
- Restrict file permissions.
- Keep sensitive files outside the web root.

Task 5: Burp Suite Advanced

Objective: Intercept, inspect and modify HTTP requests.

Activities:

- Configured Burp Suite Proxy.
- Intercepted DVWA login requests.
- Inspected HTTP parameters.
- Modified test parameters using Repeater.
- Configured Intruder payload positions.
- Performed controlled input fuzzing.

Mitigation:

- Validate all inputs on the server.
- Implement secure session management.
- Use HTTPS.
- Apply login rate limiting.
- Monitor repeated failed authentication attempts.
- Never trust client-side parameters.

Task 6: Web Security Headers

Objective: Analyze and configure HTTP security headers.

Activities:

- Inspected HTTP response headers using curl.
- Enabled Apache mod_headers.
- Configured security headers.
- Verified the configuration.

Headers studied:

Header| Purpose
X-Content-Type-Options| Prevents MIME-type sniffing
X-Frame-Options| Helps prevent clickjacking
Content-Security-Policy| Restricts content sources
Referrer-Policy| Controls referrer information
Permissions-Policy| Restricts browser features
Strict-Transport-Security| Enforces HTTPS on supported sites

Mitigation:
Configure appropriate security headers in the web server and enforce HTTPS in production.

5. Repository Structure

ApexPlanet-Web-Application-Security/
│
├── README.md
├── .gitignore
│
├── SQL_Injection/
│   └── README.md
│
├── XSS/
│   └── README.md
│
├── CSRF/
│   └── README.md
│
├── File_Inclusion/
│   └── README.md
│
├── Burp_Suite/
│   └── README.md
│
├── Security_Headers/
│   └── README.md
│
├── Screenshots/
│   ├── SQL_Injection/
│   ├── XSS/
│   ├── CSRF/
│   ├── File_Inclusion/
│   ├── Burp_Suite/
│   └── Security_Headers/
│
└── Reports/
    └── Web_Application_Security_Report.pdf

6. Key Security Lessons

- Never trust user input.
- Use prepared statements for database queries.
- Encode untrusted output.
- Implement CSRF token validation.
- Restrict file inclusion paths.
- Inspect HTTP requests and responses.
- Configure secure HTTP response headers.

7. Conclusion

This internship task provides practical exposure to web application security testing, vulnerability identification, HTTP request analysis and mitigation techniques.

It helps develop an understanding of common web application attacks and secure development practices.

8. Disclaimer

All security testing activities are intended for educational purposes and are performed in an authorized local laboratory environment using DVWA.

No unauthorized websites or systems are targeted.

---

Author: Shravani Dhaybar
Organization: Apex Planet Software Pvt. Ltd.
Project: Web Application Security Internship Task
