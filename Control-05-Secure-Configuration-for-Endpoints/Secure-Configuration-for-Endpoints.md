Secure Configuration for Endpoints Lab

CIS Control 5 – Secure Configuration of Enterprise Assets and Software

Objective

This lab focuses on applying secure configuration standards to endpoint systems. The goal is to implement security benchmarks, disable unnecessary services, enforce password complexity policies, and document configuration changes.

Prerequisites

Basic understanding of Windows or Linux systems

Access to a test machine (Windows or Linux)

Internet access

Administrative privileges

Lab Overview

Secure configuration reduces attack surface and strengthens system defenses. This lab demonstrates practical endpoint hardening aligned with industry security benchmarks such as those provided by the Center for Internet Security.

Task 1: Apply a Security Benchmark
Windows Implementation

Open Group Policy Editor:

gpedit.msc

Navigate to:

Computer Configuration > Windows Settings > Security Settings

Apply recommended settings such as:

Account Lockout Policy

Password Policy

Audit Policy

Document all changes in a checklist.

Linux Implementation

Install security audit tool:

sudo apt-get install lynis

Run audit:

sudo lynis audit system

Modify configuration files as recommended.

Example: Disable root SSH login in:

/etc/ssh/sshd_config

Set:

PermitRootLogin no
Task 2: Disable Unnecessary Services
Windows

List services:

Get-Service

Disable non-essential services through Services Manager or PowerShell.

Linux

List services:

sudo systemctl list-units --type=service

Disable unused services (example: Bluetooth):

sudo systemctl disable bluetooth.service
Task 3: Enforce Password Complexity
Windows

Navigate to:

Computer Configuration > Windows Settings > Security Settings > Account Policies > Password Policy

Configure:

Minimum password length

Complexity requirements

Password history

Linux

Edit:

/etc/security/pwquality.conf

Example configuration:

minlen=12
dcredit=-1
ucredit=-1
lcredit=-1
ocredit=-1
Results

After completing this lab:

Secure configuration benchmarks were applied

Unnecessary services were disabled

Strong password policies were enforced

All changes were documented

Conclusion

Secure configuration is essential for reducing attack surfaces and maintaining system integrity. Applying benchmarks, limiting services, and enforcing strong authentication policies significantly strengthens endpoint security.
