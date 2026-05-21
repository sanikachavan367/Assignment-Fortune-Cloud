# Task 2 — Vulnerability Assessment & Web Application Testing
Objective
The objective of this task is to perform a vulnerability assessment and manual web application security testing on a controlled lab environment using Metasploitable 2. The goal is to identify common web application vulnerabilities such as SQL Injection, Cross-Site Scripting (XSS), misconfigurations, and missing security headers using industry-standard tools.

Target Environment:
| Target IP | 192.168.61.142|  
| Web Application| DVWA (Damn Vulnerable Web Application) |
| Platform | Kali Linux (VMware Environment) |
| Testing Type| Authorized Lab-based Security Assessment |

Tools Used:
| Tool        | Purpose                                                              |
| ----------- | -------------------------------------------------------------------- |
| Nikto       | Automated scanning for web server misconfigurations and known issues |
| DVWA        | Manual testing of common web vulnerabilities (SQLi, XSS, etc.)       |
| curl        | Inspection of HTTP headers and server responses                      |
| Web Browser | Manual exploitation and payload testing                              |


Vulnerabilities Identified
# Nikto Tool (Web Vulnerability Scanner)

Nikto is an open-source command-line tool used to perform web server vulnerability scanning. It is commonly used in penetration testing and security audits to quickly identify known security issues in web applications and servers.

Purpose of Nikto

Nikto is designed to detect:

1. Outdated web server software
2. Dangerous or exposed files
3. Misconfigurations in web servers
4. Missing security headers
5. Default or insecure server settings
6. Known vulnerabilities (based on signatures)

# 1. SQL Injection (SQLi)
Definition:
SQL Injection is a web vulnerability where an attacker injects malicious SQL queries into input fields to manipulate the database.

How it works:
When a web application does not properly validate user input, attackers can modify SQL queries sent to the database.

Example payload:
' OR '1'='1

Impact:
1. Unauthorized login bypass
2. Data theft (users, passwords, emails)
3. Data modification or deletion
4. Full database compromise

Prevention:
1. Use prepared statements
2. Input validation
3. Stored procedures
4. Least privilege database access

# 2. Cross-Site Scripting (XSS)
Definition:
XSS is a vulnerability where attackers inject malicious JavaScript into web pages viewed by other users.

Types:
1. Stored XSS (saved in database)
2. Reflected XSS (comes from request)
3. DOM-based XSS (client-side manipulation)

Example payload:
<script>alert('XSS')</script>

Impact:
1. Session hijacking
2. Cookie theft
3. Defacement of websites
4. Redirecting users to malicious sites

Prevention:
1. Input sanitization
2. Output encoding
3. Content Security Policy (CSP)
4. Avoid direct execution of user input

# Conclusion
This task demonstrated vulnerability assessment and web application testing using tools like Nikto and manual testing techniques in a legal lab environment. Vulnerabilities such as SQL Injection, XSS, insecure headers, and weak authentication issues were identified and analyzed. The findings highlighted the importance of secure coding, proper server configuration, regular patching, and continuous security testing to protect web applications from cyber threats.
