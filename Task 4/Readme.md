# Task 4: Malware, System Security & Cloud Security
Objective
The objective of this task is to study malware categories, perform malware analysis documentation, demonstrate Windows and Linux system hardening techniques, research security technologies such as firewall, IDS/IPS, SIEM, and cloud security, and compare offensive and defensive cybersecurity practices.

Lab Environment 
1. Host OS: Windows 10
2. Virtualization: VMware
3. Target Machines: Kali Linux, Metasploitable

# Section 1: Malware Analysis Documentation
Malware (Malicious Software) refers to software intentionally designed to damage, disrupt, steal data, or gain unauthorized access to computer systems.

| Malware Type   | Description                                              |
| -------------- | -------------------------------------------------------- |
| Virus          | Attaches itself to files and spreads when executed       |
| Worm           | Self-replicates across networks without user interaction |
| Trojan         | Disguises itself as legitimate software                  |
| Ransomware     | Encrypts files and demands payment                       |
| Spyware        | Collects user information secretly                       |
| Rootkit        | Hides malicious processes and files                      |
| Keylogger      | Records keyboard input                                   |
| Botnet Malware | Turns infected systems into remotely controlled bots     |

# Section 2: Windows Hardening Basics
Security Measures Implemented:
1. Enable Windows Firewall
2. Disable unnecessary services
3. Enable automatic updates
4. Configure password policy
5. Enable BitLocker
6. Disable guest account
7. Configure Defender Antivirus

# Section 4: Firewall, IDS/IPS, SIEM & Cloud Security 
# 1. Firewall
Definition
A firewall is a network security device or software that monitors and filters incoming and outgoing network traffic based on predefined security rules.
Firewalls act as a barrier between trusted internal networks and untrusted external networks such as the internet.

Firewall Features:
1. Traffic filtering
2. Access control
3. Port blocking
4. Intrusion prevention
5. Application control
6. VPN support
7. Logging and monitoring

Firewall Commands:
sudo ufw enable
sudo ufw status
sudo ufw allow 22/tcp
sudo ufw deny 23/tcp

# 2. IDS/IPS (Intrusion Detection & Prevention Systems)
* IDS Definition
  An Intrusion Detection System (IDS) monitors network or system activities and generates alerts when suspicious behavior is detected.

* IPS Definition
  An Intrusion Prevention System (IPS) not only detects attacks but also actively blocks malicious traffic automatically.

Difference Between IDS and IPS
| IDS                   | IPS                        |
| --------------------- | -------------------------- |
| Detects attacks       | Detects and blocks attacks |
| Passive monitoring    | Active prevention          |
| Generates alerts      | Drops malicious packets    |
| Does not stop traffic | Stops malicious activity   |

# 3. SIEM (Security Information and Event Management)
Definition
SIEM solutions collect, analyze, and correlate logs from multiple devices and applications to detect security incidents in real time.

SIEM Functions:
1. Log collection
2. Event correlation
3. Threat detection
4. Alert generation
5. Compliance monitoring
6. Incident investigation

SIEM Workflow:
1. Collect logs from systems and applications
2. Normalize and store logs
3. Analyze events using correlation rules
4. Generate alerts for suspicious activities
5. Support incident response investigations

# 4. Cloud Security
Definition
Cloud security refers to technologies, controls, policies, and services designed to protect cloud systems, applications, and data.

Common Cloud Security Risks:
1. Misconfigured cloud storage
2. Weak IAM policies
3. Insecure APIs
4. Data breaches
5. Insider threats
6. Lack of encryption



