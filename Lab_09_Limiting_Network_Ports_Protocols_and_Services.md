# Lab 09 — Limiting Network Ports, Protocols & Services

## Objective
To identify open network ports on a Linux system, restrict unnecessary services using firewall rules, and validate system security improvements.

---

## Tools & Environment
- Ubuntu Linux (Test VM)
- Terminal
- UFW (Uncomplicated Firewall)
- iptables

---

## Task 1 — Identify Open Ports

### Using netstat

```bash
sudo netstat -tuln
```

Options:
- `-t` → TCP ports
- `-u` → UDP ports
- `-l` → Listening ports
- `-n` → Numeric addresses

### Using ss (Modern Alternative)

```bash
sudo ss -tuln
```

### Findings
Reviewed all listening ports and identified active services.
Checked for unnecessary or insecure services (e.g., Telnet on port 23).

✅ Result: Documented open ports before applying restrictions.

---

## Task 2 — Block Unused or Insecure Ports

### Example: Blocking Telnet (Port 23)

Telnet is insecure because it transmits data in plaintext.

---

### Method 1 — Using UFW (Recommended for Ubuntu)

Check firewall status:

```bash
sudo ufw status
```

Block Port 23:

```bash
sudo ufw deny 23
```

Reload firewall:

```bash
sudo ufw reload
```

---

### Method 2 — Using iptables

Block TCP Port 23:

```bash
sudo iptables -A INPUT -p tcp --dport 23 -j DROP
```

Save rules:

```bash
sudo iptables-save > /etc/iptables/rules.v4
```

✅ Result: Port 23 successfully blocked.

---

## Task 3 — Verification

Re-check open ports:

```bash
sudo ss -tuln
```

Confirmed:
- Port 23 no longer accessible externally
- No unintended services running
- Firewall rules active

---

## Key Security Concepts Learned

- Open port enumeration
- Service exposure risks
- Firewall rule configuration
- Difference between UFW and iptables
- Principle of Least Privilege (network level)
- Hardening system attack surface

---

## Security Impact

Before:
- All default listening ports exposed.

After:
- Insecure services restricted.
- Reduced attack surface.
- Improved network security posture.

---

## Conclusion

In this lab, I identified active network ports and restricted access to unnecessary services using firewall configurations. Blocking insecure ports such as Telnet (23) reduced the system’s exposure to network-based attacks. Regular port auditing and firewall management are critical components of system hardening and defensive security operations.
