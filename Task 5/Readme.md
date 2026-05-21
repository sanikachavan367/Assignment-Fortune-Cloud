# Task 5: Final Security Audit & Documentation Project

Objective:
The objective of this task was to perform a complete security assessment of the Metasploitable 2 lab environment by combining reconnaissance, scanning, vulnerability assessment, exploitation, password auditing, packet analysis, and reporting techniques covered in Tasks 1 to 4.

Target Details:
| Field            | Value                                            |
| ---------------- | ------------------------------------------------ |
| Target IP        | 192.168.61.142                                 |
| Hostname         | metasploitable.localdomain                       |
| Operating System | Linux 2.6.x (Ubuntu 8.04)                        |
| Environment      | VMware Lab Environment (Authorized Testing Only) |
| Tester           | Sanika                                           |
| Date             | 21 May 2026                                      |

# Methodology

The assessment followed standard penetration testing phases:
___
## 1. Reconnaissance
* WHOIS
* nslookup
* theHarvester
* recon-ng
  
## 2. Scanning & Enumeration
* Host discovery
* Port scanning
* Service detection
* OS fingerprinting using Nmap
  
## 3. Vulnerability Assessment
* Web vulnerability scanning using Nikto
* Nmap vulnerability scripts
* Manual web testing on DVWA
  
## 4. Exploitation & Validation
* SQL Injection testing
* Cross-Site Scripting (XSS)
* Password brute force testing using Hydra
* Backdoor verification

## 5. Post Exploitation
* Validation of unauthorized access
* Root-level shell confirmation
## 6. Reporting
* Documentation of findings, severity, risks, and mitigation steps

# Attack Surface Analysis
## Network Layer
* 23 open TCP ports identified
* Multiple outdated and vulnerable services running
* No firewall restrictions detected
* SMB signing disabled, allowing possible interception attacks
## Web Application Layer
* Apache 2.2.8 detected (End-of-Life version)
* PHP 5.2.4 exposed in HTTP headers
* DVWA accessible using default credentials
* SQL Injection and XSS vulnerabilities confirmed
* phpMyAdmin publicly accessible
* phpinfo.php exposed sensitive server configuration details
## Authentication Layer
* Anonymous FTP login enabled
* Default credentials accepted on multiple services
* No account lockout mechanism implemented
* Telnet transmitting credentials in plain text

# Critical Findings
## Finding 1 — vsftpd 2.3.4 Backdoor (CVE-2011-2523)
| Field    | Detail        |
| -------- | ------------- |
| Port     | 21/tcp        |
| CVE      | CVE-2011-2523 |
| Severity | Critical      |
| Status   | Confirmed     |

The installed version of vsftpd contains a known backdoor vulnerability that can allow unauthorized remote access. Testing confirmed the presence of the vulnerability in the lab environment.

Risk:
* Remote command execution
* Full system compromise
* Privilege escalation

Mitigation:
* Remove vulnerable vsftpd version immediately
* Upgrade to a supported secure version
* Disable anonymous FTP access

## Finding 2 — Insecure Root Shell Service
| Field    | Detail     |
| -------- | ---------- |
| Port     | 2049/tcp   |
| Severity | Critical   |
| Status   | Accessible |

An intentionally insecure service provided direct shell access without authentication.

Risk:
* Unauthorized root access
* Complete system compromise

Mitigation:
* Disable the service immediately
* Restrict unauthorized ports using firewall rules

## Finding 3 — SQL Injection (DVWA)
| Field       | Detail    |
| ----------- | --------- |
| Application | DVWA      |
| Severity    | Critical  |
| Status      | Confirmed |

Manual testing identified SQL Injection vulnerabilities in DVWA input fields.

Impact:
* Database disclosure
* Unauthorized data manipulation
* Authentication bypass

Mitigation:
* Use parameterized queries
* Implement input validation
* Avoid dynamic SQL queries

## Finding 5 — Cross-Site Scripting (XSS)
| Field       | Detail    |
| ----------- | --------- |
| Application | DVWA      |
| Severity    | High      |
| Status      | Confirmed |

Cross-Site Scripting vulnerabilities were successfully demonstrated in the lab environment.

Impact:
* Session hijacking
* Client-side script execution
* User redirection attacks

Mitigation:
* Sanitize user input
* Apply output encoding
* Implement Content Security Policy (CSP)

## Finding 6 — Weak Credentials & Brute Force Exposure
| Field     | Detail                      |
| --------- | --------------------------- |
| Service   | FTP                         |
| Tool Used | Hydra                       |
| Severity  | High                        |
| Status    | Weak credentials identified |

Weak/default credentials were successfully identified during password auditing.

Mitigation:
* Enforce strong password policies
* Disable default accounts
* Implement account lockout controls

## Finding 7 — Missing HTTP Security Headers

The following security headers were missing:
* X-Frame-Options
* X-Content-Type-Options
* Content-Security-Policy

Risk:
* Clickjacking
* MIME sniffing
* Increased XSS exposure
* Information leakage

Mitigation:
* Configure security headers in Apache
* Hide server and PHP version information
* X-XSS-Protection

# Recommendations
1. Keep Metasploitable isolated in lab environments only
2. Patch all outdated services and applications
3. Disable insecure services such as Telnet and FTP
4. Remove vulnerable backdoors and unnecessary services
5. Configure firewall rules to restrict access
6. Implement IDS/IPS monitoring solutions
7. Add missing HTTP security headers
8. Enforce strong password policies
9. Remove default credentials
10. Restrict access to phpMyAdmin and phpinfo.php
11. Deploy centralized logging and SIEM monitoring

# Conclusion

This final security audit demonstrated a complete penetration testing workflow in an authorized lab environment using Metasploitable 2. The assessment combined reconnaissance, vulnerability scanning, exploitation, password auditing, traffic analysis, and reporting techniques from Tasks 1 through 4.

The testing identified multiple critical vulnerabilities across the network, web application, and authentication layers, including outdated services, weak credentials, SQL Injection, Cross-Site Scripting, insecure configurations, and exposed backdoors.

The results highlight the importance of regular vulnerability assessments, secure configurations, strong authentication controls, patch management, and continuous monitoring in maintaining a secure infrastructure.
