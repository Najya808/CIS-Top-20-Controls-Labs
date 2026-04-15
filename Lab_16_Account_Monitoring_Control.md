Lab 16 — Account Monitoring & Control
Objective

To monitor and manage user accounts on a Linux system by identifying active/service accounts, disabling unnecessary users, and enforcing session security policies.

Tools & Environment
Ubuntu / Linux (Test VM)
Terminal
Linux User Management Commands
PAM (Pluggable Authentication Modules)
Task 1 — List and Analyze User Accounts
Step 1: View All Accounts
cat /etc/passwd
Reviewed all system and user accounts
Identified account details (UID, GID, shell, home directory)
Step 2: Identify Service Accounts
awk -F: '$3 < 1000 {print $1}' /etc/passwd
Listed non-human/service accounts
Distinguished system accounts from regular users

✅ Result: User and service accounts successfully identified.

Task 2 — Disable or Remove Unnecessary Accounts
Step 1: Identify Obsolete Accounts
Reviewed accounts not in use (e.g., inactive users)
Step 2: Disable Account
sudo usermod -L username
Locked account to prevent login
Step 3: Remove Account (if required)
sudo userdel username

⚠️ Action irreversible — verified before removal

✅ Result: Unnecessary accounts disabled or removed.

Task 3 — Implement Session Timeout & Lockout Policies
Step 1: Configure Session Timeout
echo "export TMOUT=300" | sudo tee -a /etc/profile
Set auto logout after 300 seconds of inactivity
Step 2: Apply Configuration
source /etc/profile
Step 3: Configure Account Lockout Policy
Edited PAM configuration:
sudo nano /etc/pam.d/common-auth
Added:
auth required pam_tally2.so deny=5 unlock_time=600 onerr=fail audit even_deny_root
Locks account after 5 failed login attempts
Unlocks after 10 minutes

✅ Result: Session timeout and brute-force protection enforced.

Key Security Concepts Learned
User account auditing
Service vs human account identification
Account disabling and removal
Session timeout enforcement
Brute-force attack mitigation using PAM
Security Impact
Before:
Unused accounts may remain active
No session timeout or lockout policy
Increased risk of unauthorized access
After:
Inactive accounts disabled/removed
Session timeout enforced
Account lockout prevents brute-force attacks
Conclusion

In this lab, I monitored and controlled user accounts by identifying unnecessary accounts, enforcing account restrictions, and implementing session security policies. These measures significantly improve system security and help prevent unauthorized access in a SOC environment.
