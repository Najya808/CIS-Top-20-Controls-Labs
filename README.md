# CIS-Top-20-Controls-Labs
A hands-on implementation of the CIS Critical Security Controls framework.  This repository contains practical labs demonstrating defensive security strategies including system hardening, logging, monitoring, vulnerability management, and threat detection.

- [Lab 01 — Hardware Asset Inventory](Hardware-Asset-Inventory.md)  
  What I learned: how to create and maintain a structured hardware asset inventory aligned with CIS Control 1, assign ownership to enterprise devices, and validate asset visibility using Nmap network scanning to detect authorized and unauthorized devices.

- [Lab 02 — Software Asset Inventory](Software-Asset-Inventory.md)  
  What I learned: how to inventory installed software on Windows and Linux using native command-line tools, export data for structured analysis, and identify unknown or end-of-life applications that may introduce security risks.

- [Lab 03 — Basic Vulnerability Scanning](Basic-Vulnerability-Scanning.md)  
  What I learned: how to install and configure OpenVAS, perform a controlled vulnerability scan, analyze high and critical findings, and document remediation steps aligned with continuous vulnerability management practices.

- [Lab 04 — Controlled Use of Administrative Privileges](Controlled-Use-of-Administrative-Privileges.md)  
  What I learned: how to audit administrative accounts on a Linux system, enforce the principle of least privilege by removing unnecessary sudo access, document security changes, and verify system stability after privilege modifications.

- [Lab 05 — Secure Configuration for Endpoints](Secure-Configuration-for-Endpoints.md)  
  What I learned: how to apply security benchmarks to Windows and Linux systems, harden endpoints by disabling unnecessary services, enforce strong password policies, and document configuration changes aligned with secure configuration best practices.

- [Lab 06 — Monitoring & Analysis of Audit Logs](Lab_06_Monitoring_Analysis_of_Audit_Logs.md)  
  What I learned: how to enable verbose audit logging on Windows and Linux systems, collect and centralize security logs, and analyze authentication events to detect suspicious activities such as brute-force login attempts and logon failures.

- [Lab 07 — Securing Email & Web Browsers](Lab_07_Securing_Email_and_Web_Browsers.md)  
  What I learned: how to configure phishing protection in an email client, install browser security extensions like script and ad blockers, and harden browser privacy settings to reduce exposure to web-based threats.

- [Lab 08 — Malware Defenses](Lab_08_Malware_Defenses.md)  
  What I learned: how to install and configure anti-malware software, update virus signatures, perform system scans, and analyze quarantine logs to evaluate malware detection effectiveness.

- [Lab 09 — Limiting Network Ports, Protocols & Services](Lab_09_Limiting_Network_Ports_Protocols_and_Services.md)  
  What I learned: how to identify open network ports using netstat/ss, restrict insecure services like Telnet via firewall rules, and validate system hardening through port re-verification.
  
- [Lab 10 — Data Recovery Capabilities](Lab_10_Data_Recovery_Capabilities.md)  
  What I learned: how to perform manual and automated backups using tar and cron, restore archived data, and verify integrity using diff to ensure disaster recovery readiness.

- [Lab 11 — SSH Hardening & Secure Remote Access](Lab_11_SSH_Hardening_and_Secure_Access.md)  
  What I learned: how to secure SSH by disabling root and password-based login, implementing key-based authentication, and reducing brute-force attack risks through configuration hardening.

- [Lab 12 — Boundary Defense](Lab_12_Boundary_Defense.md)  
  What I learned: how to document network boundaries, configure firewall rules using UFW, and test defenses by simulating unauthorized access attempts.

- [Lab 13 — Data Protection Basics](Lab_13_Data_Protection_Basics.md)  
  What I learned: how to encrypt files with AES, enable secure communications using HTTPS and SSH, and validate encryption effectiveness to protect data confidentiality and integrity.

- [Lab 14 — Controlled Access Based on Need to Know](Lab_14_Controlled_Access.md)  
  What I learned: how to enforce least privilege by assigning directory permissions to specific users/groups and validating access through authorized and unauthorized testing.

- [Lab 15 — Wireless Access Control](Lab_15_Wireless_Access_Control.md)  
  What I learned: how to secure a wireless network using WPA2/WPA3 encryption, disable WPS, and verify that only authorized users can connect.

- [Lab 16 — Account Monitoring & Control](Lab_16_Account_Monitoring_Control.md)  
  What I learned: how to audit user accounts, disable or remove unnecessary users, and implement session timeout and lockout policies to prevent unauthorized access.

- [Lab 17 — Security Awareness Training](Lab_17_Security_Awareness_Training.md)  
  What I learned: how to create security awareness training, test user knowledge with quizzes, and identify human security gaps to reduce risks like phishing and social engineering.
