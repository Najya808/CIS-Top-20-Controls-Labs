# Lab 06 — Monitoring & Analysis of Audit Logs

## Objective
To enable, collect, and analyze audit logs on Windows and Linux systems in order to detect suspicious activity and strengthen endpoint monitoring.

---

## Tools & Environment
- Windows 10 / 11 (Test VM)
- Ubuntu Linux (Test VM)
- Event Viewer
- Local Security Policy
- rsyslog
- grep
- Terminal

---

## Task 1 — Enable Verbose Logging

### Windows Configuration

**Step 1 — Open Event Viewer**
- Press `Win + R`
- Type `eventvwr`
- Navigate to:
  Windows Logs → Security

**Step 2 — Enable Audit Policies**
- Open `Local Security Policy`
- Navigate to:
  Security Settings → Local Policies → Audit Policy
- Enable:
  - Audit account logon events (Success, Failure)
  - Audit logon events (Success, Failure)

✅ Result: Windows now logs both successful and failed login attempts.

---

### Linux Configuration

**Step 1 — Configure rsyslog**
```bash
sudo nano /etc/rsyslog.conf
```

Ensure this line exists:
```
auth.* /var/log/auth.log
```

**Step 2 — Restart Service**
```bash
sudo systemctl restart rsyslog
```

✅ Result: Authentication logs are now stored in `/var/log/auth.log`.

---

## Task 2 — Collect Logs

### Linux
```bash
mkdir ~/log_analysis
cp /var/log/auth.log ~/log_analysis/
cd ~/log_analysis
```

### Windows
- Open Event Viewer
- Right-click Security logs
- Select “Save All Events As”
- Save as `.evtx` file

✅ Result: Logs centralized for analysis.

---

## Task 3 — Analyze Logs

### Linux — Detect Failed Logins
```bash
grep 'Failed' auth.log
```

### Windows
- Open saved `.evtx` file
- Use Filter Current Log
- Search for:
  - “Logon Failure”
  - Event ID 4625 (Failed Logon)

---

## Findings

- Multiple failed login attempts indicate possible brute-force activity.
- Successful logins after repeated failures may indicate compromised credentials.
- Log monitoring is essential for early threat detection.

---

## Key Security Concepts Learned

- Importance of audit logging
- Difference between successful vs failed login tracking
- How brute-force attacks appear in logs
- Basic log filtering techniques
- Importance of centralized log collection

---

## Conclusion

This lab strengthened my understanding of endpoint monitoring and audit logging. By enabling detailed logging, collecting logs, and analyzing suspicious patterns, I practiced real-world SOC-level monitoring techniques essential for threat detection and incident response.
