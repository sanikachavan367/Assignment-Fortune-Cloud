# Task 3 — Password Security, Sniffing & Session Analysis
Objective:
The objective of this task is to analyze network traffic, perform password auditing in a controlled lab environment, and understand secure and insecure session management concepts. The task also demonstrates the risks associated with session hijacking and weak authentication mechanisms.

Lab Environment
Platform: Kali Linux on VMware
Target Machine: Metasploitable 2 
Testing Type: Authorized Local Lab Testing

Tools Used
| Tool            | Purpose                                |
| --------------- | -------------------------------------- |
| Wireshark       | Packet capturing and traffic analysis  |
| Hydra           | Brute-force login testing in lab setup |
| Browser         | Session and cookie analysis            |

# Activities Performed
# 1. Packet Capture & Traffic Analysis

Using Wireshark, network packets were captured and analyzed for:
1. HTTP traffic
2. DNS queries
3. TCP communication
4. ARP packets

The analysis helped identify unencrypted communication, request-response behavior, and basic network interactions.

# 2. Password Auditing

Password auditing was performed in a legal lab environment using Hydra to test password strength and identify weak credentials.
Example Commands:
hydra -l admin -P passwords.txt ftp://target-ip

# Risks of Session Hijacking

Session hijacking allows attackers to gain unauthorized access by stealing active session tokens.

Major Risks:
1. Unauthorized account access
2. Session theft
3. User impersonation
4. Sensitive data exposure

Common Causes:
1. Unencrypted HTTP traffic
2. Weak session management
3. Packet sniffing attacks
4. XSS vulnerabilities
