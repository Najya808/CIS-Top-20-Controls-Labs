# Lab 11 — SSH Hardening & Secure Remote Access

## Objective
To secure remote access by hardening SSH configuration, disabling insecure authentication methods, and reducing the risk of brute-force attacks.

---

## Tools & Environment
- Ubuntu Linux (Test VM)
- OpenSSH Server
- Terminal

---

## Task 1 — Install & Verify SSH Service

### Install SSH Server

```bash
sudo apt-get update
sudo apt-get install openssh-server
```

### Check SSH Status

```bash
sudo systemctl status ssh
```

✅ Result: SSH service installed and running.

---

## Task 2 — Harden SSH Configuration

### Open SSH Config File

```bash
sudo nano /etc/ssh/sshd_config
```

### Apply Security Changes

Modify or add:

```
PermitRootLogin no
PasswordAuthentication no
PermitEmptyPasswords no
MaxAuthTries 3
```

Explanation:
- Disable root login → prevents direct admin attacks  
- Disable password login → forces key-based authentication  
- Limit login attempts → slows brute-force attacks  

---

### Restart SSH Service

```bash
sudo systemctl restart ssh
```

✅ Result: Secure SSH configuration applied.

---

## Task 3 — Implement Key-Based Authentication

### Generate SSH Key (on client machine)

```bash
ssh-keygen
```

### Copy Key to Server

```bash
ssh-copy-id user@server-ip
```

### Test Login

```bash
ssh user@server-ip
```

✅ Result: Login works without password.

---

## Task 4 — Verify Security Improvements

- Root login disabled ✅  
- Password authentication disabled ✅  
- Only key-based login allowed ✅  
- Limited login attempts enforced ✅  

---

## Key Security Concepts Learned

- SSH hardening techniques  
- Brute-force attack prevention  
- Key-based authentication  
- Secure remote access principles  
- Reducing attack surface  

---

## Security Impact

Before:
- SSH vulnerable to brute-force attacks  
- Password-based login enabled  

After:
- Strong authentication enforced  
- Attack surface reduced  
- Remote access secured  

---

## Conclusion

In this lab, I secured SSH by disabling insecure authentication methods and enforcing key-based access. This significantly reduces the risk of unauthorized access and brute-force attacks, making it a critical step in securing Linux systems.
