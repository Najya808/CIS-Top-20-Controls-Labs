# Lab 20 — Penetration Testing & Red Team Exercises

## Objective
Understand the basic concepts of penetration testing and red team exercises, use open-source tools to identify network vulnerabilities, and practice detecting misconfigurations while documenting security improvements.

---

## Tools & Environment
- Kali Linux / Ubuntu VM
- Nmap
- Metasploit Framework
- Target VM (intentionally vulnerable or lab environment)
- Terminal / CLI access

---

## Tasks

---

### Task 1 — Network Scanning with Nmap

#### Step 1.1 — Understanding Nmap
Nmap (Network Mapper) is an open-source tool used for network discovery and security auditing.

**Key Concepts:**
- Port scanning
- Service enumeration
- Host discovery
- Network reconnaissance

---

#### Step 1.2 — Install Nmap

```bash id="n1p4ab"
sudo apt-get update
sudo apt-get install nmap
Step 1.3 — Basic Network Scan

Objective:
Identify open ports and running services on a target system.

nmap -sV <target-ip>

Explanation:

-sV detects service versions
Helps identify outdated or vulnerable services
Provides initial attack surface mapping
Task 2 — Vulnerability Scanning with Metasploit
Step 2.1 — Introduction to Metasploit

Metasploit Framework is a penetration testing platform used to identify, validate, and exploit vulnerabilities.

Key Concepts:

Exploits
Payloads
Auxiliary scanners
Vulnerability validation
Step 2.2 — Launch Metasploit Console
msfconsole
Step 2.3 — SMB Vulnerability Scanning

Objective:
Identify vulnerable SMB services on a target system.

use auxiliary/scanner/smb/smb_version
set RHOSTS <target-ip>
run

Security Insight:

Detects outdated SMB versions
Helps identify potential lateral movement paths
Useful for early-stage reconnaissance
Task 3 — Controlled Exploitation of Misconfigurations
Step 3.1 — Identify Misconfigurations

Common issues include:

Default credentials
Outdated services
Unpatched software
Exposed services (FTP, SMB, Telnet)
Step 3.2 — Ethical Warning

All testing must be performed only in authorized lab environments.

Step 3.3 — Example Exploit (Benign Lab Use)
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOST <target-ip>
exploit

Explanation:

Targets known vulnerable FTP service
Demonstrates impact of unpatched systems
Used strictly for educational lab environments
Key Security Concepts
Penetration testing lifecycle
Network reconnaissance
Service enumeration
Vulnerability validation
Exploit execution (controlled lab use)
Misconfiguration risks
Security Impact

Penetration testing helps simulate real-world attacker behavior, revealing weaknesses before exploitation occurs in production environments. It strengthens defensive security posture by exposing misconfigurations and outdated services.

Conclusion

This lab demonstrated foundational red team techniques using Nmap and Metasploit. It highlighted how attackers discover services, identify vulnerabilities, and exploit misconfigurations, reinforcing the importance of patching, secure configuration, and continuous monitoring.
