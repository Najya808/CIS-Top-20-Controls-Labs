# Lab 22 — Secure Cloud Instance (Basic)

## Objective
Understand how to deploy a secure cloud virtual machine, restrict inbound network access, implement Multi-Factor Authentication (MFA), and document security configurations for audit and compliance purposes.

---

## Tools & Environment
- Cloud platform (OpenStack / AWS / Azure / GCP equivalent)
- Ubuntu / CentOS image
- Security Groups / Firewall rules
- MFA app (Google Authenticator / Authy)
- SSH client (optional)

---

## Tasks

---

### Task 1 — Launch a Secure Cloud VM

#### Step 1.1 — Access Cloud Console
- Log in to cloud provider dashboard

---

#### Step 1.2 — Select Image & Instance Type
- Choose Linux-based OS (Ubuntu / CentOS)
- Select small instance (cost-efficient, minimal attack surface)

---

#### Step 1.3 — Configure Instance
- Set instance name
- Select region & availability zone
- Apply default secure settings

---

#### Step 1.4 — Launch Instance
- Review configuration
- Launch VM securely

---

## Task 2 — Restrict Inbound Ports (Security Hardening)

### Allowed Ports Only:
- 22 (SSH)
- 80 (HTTP)
- 443 (HTTPS)

---

#### Example Security Group Rules (CLI)

```bash id="c22sg1"
openstack security group rule create --protocol tcp --dst-port 22:22 --remote-ip 0.0.0.0/0 <security-group-id>
openstack security group rule create --protocol tcp --dst-port 80:80 --remote-ip 0.0.0.0/0 <security-group-id>
openstack security group rule create --protocol tcp --dst-port 443:443 --remote-ip 0.0.0.0/0 <security-group-id>
Security Insight:
Reduces attack surface
Blocks unnecessary services
Enforces least privilege networking
Task 3 — Enable Multi-Factor Authentication (MFA)
Step 3.1 — Access Security Settings
Open account security dashboard
Step 3.2 — Enable MFA
Scan QR code using MFA app
Link account to authentication app
Step 3.3 — Test MFA
Logout and re-login
Verify second authentication factor is required
Security Insight:
Prevents account takeover even if password is compromised
Adds strong identity verification layer
Task 4 — Document Security Configuration
Example Security Group Documentation
Protocol	Port Range	Source	Description
TCP	22	0.0.0.0/0	SSH Access
TCP	80	0.0.0.0/0	HTTP Access
TCP	443	0.0.0.0/0	HTTPS Access
Key Security Concepts
Cloud security fundamentals
Security groups / firewall rules
Least privilege networking
Multi-Factor Authentication (MFA)
Secure VM provisioning
Security Impact

Proper cloud instance configuration significantly reduces exposure to external threats. Restricting ports and enabling MFA protects against unauthorized access, brute-force attacks, and misconfigurations.

Conclusion

This lab demonstrated how to securely deploy and configure a basic cloud VM. You implemented essential cloud security practices including firewall restriction, MFA enforcement, and configuration documentation—key skills for SOC and cloud security roles.
