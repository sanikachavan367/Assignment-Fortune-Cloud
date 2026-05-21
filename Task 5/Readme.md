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
## 3. Exploitation & Validation
* SQL Injection testing
* Cross-Site Scripting (XSS)
* Password brute force testing using Hydra
* Backdoor verification
