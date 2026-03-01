# Lab 07 — Securing Email & Web Browsers

## Objective
To enhance endpoint security by configuring phishing protection in email clients, implementing browser security extensions, and modifying unsafe default browser settings.

---

## Tools & Environment
- Ubuntu Linux (Test VM)
- Thunderbird Email Client
- Mozilla Firefox Browser
- NoScript Extension
- uBlock Origin Extension

---

## Task 1 — Enable Phishing Filters in Email Client

### Install Thunderbird (Linux)
```bash
sudo apt-get install thunderbird
```

### Configure Junk & Phishing Protection

1. Open Thunderbird.
2. Navigate to:
   Tools → Account Settings → Junk Settings
3. Enable:
   - Adaptive junk mail controls
   - Trust junk mail headers set by

### Testing Phishing Detection
- Sent a simulated phishing email (safe test sample).
- Verified that Thunderbird flagged it as Junk/Phishing.

✅ Result: Email client now actively filters suspicious messages.

---

## Task 2 — Install Browser Security Plugins

### Install Firefox (Linux)
```bash
sudo apt-get install firefox
```

### Install Security Extensions

1. Open Firefox.
2. Go to:
   Menu → Add-ons and Themes

**Installed:**
- NoScript (Script Blocker)
- uBlock Origin (Ad & Pop-up Blocker)

### Testing Extensions
- Visited ad-heavy website.
- Verified:
  - Pop-ups blocked
  - Scripts restricted
  - Ads filtered

✅ Result: Reduced attack surface from malicious scripts and ads.

---

## Task 3 — Harden Browser Default Settings

### Modified Settings (Firefox)

Navigate to:
Settings → Privacy & Security

Changed:

- Enhanced Tracking Protection → Set to **Strict**
- Deceptive Content and Dangerous Software Protection → Enabled
- Block Fingerprinting → Enabled

### Documentation Checklist

| Setting Modified | Action Taken | Security Benefit |
|------------------|-------------|------------------|
| Tracking Protection | Set to Strict | Reduces tracking & malicious scripts |
| Dangerous Content Protection | Enabled | Blocks known malicious sites |
| Fingerprinting Protection | Enabled | Prevents advanced tracking |

---

## Key Security Concepts Learned

- Phishing detection mechanisms
- Adaptive junk filtering
- Script blocking & ad filtering
- Browser fingerprinting risks
- Reducing web-based attack surfaces

---

## Conclusion

This lab strengthened my understanding of email and browser security hardening. By enabling phishing filters, installing protective browser extensions, and modifying insecure default settings, I reduced the risk of phishing attacks, malicious scripts, and online tracking. These controls are essential for protecting end users against common web-based threats.
