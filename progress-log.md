# Day 1 – Lab Environment Set

-- Installed and verified VMware Workstation as the virtualization platform for creating the cybersecurity lab environment.

-- Set up Kali Linux as the attacker machine. Ensured the system is running properly and ready for performing security testing and analysis.

-- Installed Metasploitable2 as the target machine. This vulnerable machine will be used to practice penetration testing techniques in a safe and controlled environment.

-- Understood the purpose of using vulnerable machines like Metasploitable2 and DVWA for ethical hacking practice.

-- Configured a private network using Host-Only Adapter to ensure isolated communication between attacker (Kali Linux) and target (Metasploitable2).

-- Verified network connectivity between machines using basic commands like ping to confirm successful lab setup.

-- Gained understanding of how isolated lab environments help in safe cybersecurity experimentation without affecting external systems.

-- Successfully completed initial lab setup required for further cybersecurity tasks.

 Outcome:  A fully functional virtual lab environment with attacker and target machines ready for testing.


# Day 2 – Cybersecurity Basics

-- Studied the CIA Triad, which is the core foundation of cybersecurity:

   -- Confidentiality:
      Ensuring that sensitive information is accessible only to authorized users.
      Learned about methods like encryption, authentication, and access control to protect data from unauthorized access.

   -- Integrity:
      Ensuring that data remains accurate, consistent, and unaltered during storage or transmission.
      Explored how hashing and validation mechanisms help detect unauthorized changes.

   -- Availability:
      Ensuring that systems, networks, and data are available to users when required.
      Understood how backups, redundancy, and protection against attacks like DDoS help maintain availability.

-- Explored different types of cyber threats in detail:

   -- Phishing:
      A social engineering attack where attackers trick users into revealing sensitive information through fake emails or websites.

   -- Malware:
      Malicious software designed to damage or gain unauthorized access to systems, including viruses, worms, and trojans.

   -- Ransomware:
      A type of malware that encrypts user data and demands payment for decryption, causing serious financial and operational damage.

   -- Distributed Denial of Service (DDoS):
      An attack where multiple systems flood a target server with traffic, making it unavailable to legitimate users.

   -- SQL Injection:
      A web-based attack where malicious SQL queries are inserted into input fields to manipulate or access database information.

   -- Brute Force Attack:
      A method where attackers try multiple combinations of usernames and passwords to gain unauthorized access.

-- Understood the real-world impact of these attacks:

   -- Data breaches leading to loss of sensitive information
   -- Financial losses for organizations and individuals
   -- Damage to reputation and trust
   -- Legal consequences and compliance issues

-- Learned the importance of cybersecurity best practices:

   -- Using strong and unique passwords
   -- Enabling multi-factor authentication (MFA)
   -- Keeping software and systems updated
   -- Avoiding suspicious links and emails
   -- Implementing proper security policies and awareness
   

# Day 3 – Linux Fundamentals & Essential Commands

-- Gained hands-on understanding of Linux, which is widely used in cybersecurity for penetration testing, server management, and automation  

-- Explored basic Linux file system structure:
   -- /root → Root user directory  
   -- /home → User directories  
   -- /etc → Configuration files  
   -- /var → Logs and variable data  
   -- /bin & /usr/bin → Essential system commands  

-- Learned and practiced essential Linux commands:

   -- pwd → Displays current working directory  
   -- ls → Lists files and directories  
      -- ls -l → Detailed view  
      -- ls -a → Shows hidden files  

   -- cd → Navigate between directories  
      -- cd .. → Move one level up  
      -- cd / → Go to root directory  

   -- mkdir → Create new directory  
   -- rmdir → Remove empty directory  
   -- rm -r → Delete directory with contents  

   -- touch → Create new file  
   -- cp → Copy files  
   -- mv → Move or rename files  

   -- cat → View file content  
   -- nano → Edit files in terminal  

-- Understood file permissions and security:
   -- chmod → Change file permissions  
   -- chown → Change file ownership  

   -- Permission format:
      rwx r-x r--
      (Read, Write, Execute for Owner, Group, Others)

-- Learned importance of Linux in cybersecurity:
   -- Most security tools run on Linux (especially Kali Linux)  
   -- Faster command-line operations compared to GUI  
   -- Better control over system and processes  
-- Practiced commands in Kali Linux terminal to build familiarity  


# Day 4 – Network Scanning with Nmap (Reconnaissance Phase)

-- Learned about the importance of Reconnaissance (information gathering) in cybersecurity  
   -- First step in ethical hacking before any attack  
   -- Helps identify open ports, running services, and potential vulnerabilities  

-- Understood how networks communicate using:
   -- IP Address → Identifies devices on network  
   -- Ports → Entry points for services (e.g., 80 = HTTP, 22 = SSH)  
   -- Protocols → Rules for communication (TCP/UDP)  

-- Performed practical scanning on Metasploitable2 from Kali Linux:

Basic Scan
-- Command:
   nmap 192.168.x.x  
   -- Checks if host is alive  
   -- Lists open ports  

Service Version Detection
-- Command:
   nmap -sV 192.168.x.x  
   -- Detects services running on open ports  
   -- Example:
      -- Port 21 → FTP  
      -- Port 22 → SSH  
      -- Port 80 → HTTP  
Aggressive Scan
-- Command:
   nmap -A 192.168.x.x  
   -- Detect OS details  
   -- Version detection  
   -- Script scanning  
   -- Traceroute  
Common Ports Observed
-- 21 → FTP (File Transfer)  
-- 22 → SSH (Remote Login)  
-- 23 → Telnet (Insecure remote access)  
-- 25 → SMTP (Email service)  
-- 80 → HTTP (Web server)  
-- 139/445 → SMB (Windows file sharing)  

-- Learned that open ports can be potential entry points for attackers if not secured properly  
-- Understood difference between:
   -- Open Port → Service is running and accessible  
   -- Closed Port → No service running  
   -- Filtered Port → Blocked by firewall  
-- Practiced scanning multiple times to understand output clearly  
-- Learned how attackers use scanning to:
   -- Map network structure  
   -- Identify weak services  
   -- Plan attacks  
--- Performed scans only in controlled lab environment (ethical practice)  


# Day 5 – Network Traffic Analysis using Wireshark

-- Learned about packet analysis and its importance in cybersecurity  
   -- Helps monitor, capture, and analyze network traffic  
   -- Used in detecting attacks, troubleshooting, and forensic investigations  

Understanding Packets
-- A packet is a small unit of data transmitted over a network  
-- Each packet contains:
   -- Source IP  
   -- Destination IP  
   -- Protocol (TCP, UDP, ICMP)  
   -- Payload (actual data)  

Practical Activity – Packet Capture

-- Opened Wireshark in Kali Linux  
-- Selected active network interface (eth0)  
-- Started live packet capture  

-- Generated traffic using:
   ping 192.168.x.x  

-- Observed ICMP packets in Wireshark  

Filtering Packets

-- Used filters to analyze specific traffic:

   -- ICMP traffic:
      icmp  

   -- HTTP traffic:
      http  

   -- DNS queries:
      dns  

   -- TCP traffic:
      tcp  

Packet Analysis

-- Clicked on individual packets to inspect details:
   -- Frame layer (basic info)  
   -- IP layer (source & destination)  
   -- Protocol layer (TCP/ICMP details)  

-- Observed:
   -- Request and reply packets in ping  
   -- Time delay between packets  
   -- Packet size and structure  

 Security Insights

-- Learned how attackers and defenders use packet analysis:

   -- Detect suspicious traffic  
   -- Identify malware communication  
   -- Analyze data leaks  
   -- Monitor unusual patterns  


Real-World Importance

-- Wireshark is widely used in:
   -- Security Operations Centers (SOC)  
   -- Incident response  
   -- Network troubleshooting  


# Day 6 – Web Application Testing using Burp Suite

-- Learned about Web Application Security and why websites are common attack targets  
   -- Most applications run on web (login forms, APIs, dashboards)  
   -- Attackers target input fields, authentication, and data handling  

Understanding How Web Works
-- Client (Browser) → sends request → Server  
-- Server → sends response → Client  

-- Example:
   -- Request: Login form submission  
   -- Response: Success / Failure message  

Practical Setup

-- Opened Burp Suite in Kali Linux  
-- Launched embedded browser from Burp  

-- Target used:
   http://192.168.x.x   (Metasploitable2 web server)

Intercepting Requests

-- Enabled Intercept in Burp Suite  
-- Visited the target website  

-- Observed HTTP request:
   -- GET /index.php  
   -- Headers (Host, User-Agent, etc.)  

-- Turned Intercept OFF to forward request  

Testing Login Form (DVWA)

-- Entered dummy credentials in login form  

-- Captured POST request:
   -- Username and password visible in request body  

Example:
   username=admin&password=1234  

 Understanding Vulnerabilities

-- Learned how attackers manipulate requests:

   -- Change parameters (e.g., username=admin)  
   -- Modify values before sending  
   -- Bypass authentication  

Key Concepts Learned

-- HTTP Methods:
   -- GET → fetch data  
   -- POST → send data  

-- Parameters:
   -- Data sent in request (form inputs)  

-- Headers:
   -- Additional information about request 
   
Security Insights
-- Sensitive data can be exposed if not encrypted (HTTP risk)  
-- Weak input validation leads to attacks like:
   -- SQL Injection  
   -- Authentication bypass  
-- Intercepting requests helps identify vulnerabilities  
 
