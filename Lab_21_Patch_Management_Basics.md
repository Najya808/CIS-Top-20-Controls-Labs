# Lab 21 — Patch Management Basics

## Objective
Understand the importance of patch management, learn how to check and apply system updates across Windows and Linux, and verify system stability after updates.

---

## Tools & Environment
- Windows OS (Windows Update)
- Linux (Ubuntu / CentOS / RHEL)
- Terminal / Command Line
- sudo privileges

---

## Tasks

---

### Task 1 — Checking for Available Updates

---

#### Windows

**Steps:**
- Open **Start Menu**
- Go to **Settings**
- Navigate to **Update & Security**
- Click **Windows Update**
- Select **Check for updates**

**Security Insight:**
- Identifies missing security patches
- Ensures system stays protected against known vulnerabilities

---

#### Linux (Ubuntu — apt)

```bash id="u21apt1"
sudo apt update
apt list --upgradable

Security Insight:

Updates package index
Lists available security and software upgrades
Linux (CentOS / RHEL — yum)
sudo yum check-update

Security Insight:

Checks repository for available updates
Identifies outdated system packages
Task 2 — Applying Updates
Windows
Click Install Updates
Follow installation prompts
Allow system to complete update process
Ubuntu (apt)
sudo apt upgrade -y

Log updates:

sudo apt list --upgradable >> updates_applied.log
CentOS / RHEL (yum)
sudo yum update -y

Log updates:

sudo yum list updates >> updates_applied.log
Task 3 — Reboot and Validation
Reboot System (Linux)
sudo reboot
Validate System Stability

Linux logs check:

dmesg | grep -i "error"

Windows validation:

Open Event Viewer
Check for system or application errors
Key Security Concepts
Patch management lifecycle
Vulnerability remediation
System update validation
OS hardening through updates
Change management in IT systems
Security Impact

Patch management reduces exposure to known vulnerabilities, prevents exploitation of outdated software, and ensures systems remain stable and secure against emerging threats.

Conclusion

This lab demonstrated how to identify, apply, and verify system updates on Windows and Linux systems. Regular patching is essential for maintaining system security, improving performance, and reducing attack surfaces.
