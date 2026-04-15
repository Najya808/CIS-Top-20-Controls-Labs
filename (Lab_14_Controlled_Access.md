Lab 14 — Controlled Access Based on Need to Know
Objective

To implement controlled access using the principle of least privilege by assigning permissions to specific users/groups and validating access restrictions.

Tools & Environment
Ubuntu Linux (Test VM)
Terminal
Linux File System Permissions
Task 1 — Create a "Finance" Folder
Step 1: Open Terminal
Launched terminal application
Step 2: Navigate to Home Directory
cd ~
Step 3: Create Directory
mkdir Finance

✅ Result: “Finance” directory created.

Task 2 — Assign Permissions to Specific User/Group
Step 1: Check Existing Users
cut -d: -f1 /etc/passwd
Step 2: Create User (if needed)
sudo useradd finance_user
Step 3: Create Group
sudo groupadd finance_group
Step 4: Add User to Group
sudo usermod -aG finance_group finance_user
Step 5: Assign Ownership to Group
sudo chown :finance_group Finance
Step 6: Set Directory Permissions
sudo chmod 770 Finance
Owner & group: full access (read/write/execute)
Others: no access

✅ Result: Access restricted to authorized group only.

Task 3 — Test Unauthorized Access
Step 1: Switch User
su - demo_user
Step 2: Attempt Access
cd ~/Finance
ls
Observation
Permission denied error displayed

✅ Result: Unauthorized access blocked.

Task 4 — Validate Authorized Access
Step 1: Switch Back
exit
Step 2: Test with Authorized User
su - finance_user
cd ~/Finance
ls
Observation
Access granted successfully

✅ Result: Authorized user can access directory.

Key Security Concepts Learned
Principle of least privilege
Role-based access control (RBAC) basics
Linux file permission model
User and group management
Preventing unauthorized data access
Security Impact
Before:
No access restrictions on sensitive directory
Risk of unauthorized data exposure
After:
Access limited to specific user/group
Unauthorized users blocked
Improved data confidentiality
Conclusion

In this lab, I implemented controlled access based on the need-to-know principle by assigning permissions to a specific group and validating access through testing. This ensures that only authorized users can access sensitive data, which is critical for maintaining security in a SOC environment.
