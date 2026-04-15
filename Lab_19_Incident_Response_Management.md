# Lab 19 — Incident Response & Management

## Objective
Understand the roles and responsibilities in an incident response team and learn the core incident handling lifecycle: detection, containment, eradication, and recovery. Apply these concepts through a malware infection scenario using open-source security tools.

---

## Tools & Environment
- Linux system (Ubuntu recommended)
- Suricata (Network IDS)
- ClamAV (Antivirus)
- iptables (Firewall tool)
- Terminal / CLI access

---

## Tasks

---

### Task 1 — Incident Response Roles & Responsibilities

#### Subtask 1.1 — Key Roles

**Incident Lead**
- Coordinates entire incident response process
- Makes high-level decisions during security incidents
- Ensures proper escalation and documentation

**Communication Lead**
- Manages communication between team members
- Handles external reporting and stakeholder updates
- Ensures accurate and controlled information flow

---

#### Subtask 1.2 — Responsibility Documentation

Each role must clearly define responsibilities to ensure:
- Fast coordination during incidents
- Reduced confusion during high-pressure situations
- Structured response workflow

---

### Task 2 — Incident Handling Lifecycle

---

#### Subtask 2.1 — Detection

**Concept:**
Detection identifies suspicious activity using anomaly-based or signature-based methods.

**Tool Example — Suricata:**
```bash id="f1x9qd"
sudo suricata -c /etc/suricata/suricata.yaml -i eth0

Security Insight:

Detects unusual network behavior
Flags potential intrusion attempts
Provides real-time alerts
Subtask 2.2 — Containment

Concept:
Limit the spread of an incident to reduce damage.

Example — Block Malicious IP:

sudo iptables -A INPUT -s <malicious-IP> -j DROP

Security Insight:

Prevents lateral movement
Isolates affected systems or traffic
Reduces impact radius
Subtask 2.3 — Eradication

Concept:
Remove the root cause of the incident completely.

Tool Example — ClamAV:

sudo freshclam
sudo clamscan --remove --recursive /

Security Insight:

Removes malware from system
Ensures threat is fully eliminated
Prevents reinfection
Subtask 2.4 — Recovery

Concept:
Restore systems back to normal secure operation.

Steps:

Verify system integrity
Reinstall missing patches
Restore services carefully
Monitor for anomalies

Command Example:

sudo apt-get update && sudo apt-get upgrade
Task 3 — Scenario-Based Exercise: Malware Infection
Situation

A system shows slow performance and abnormal network traffic spikes, indicating possible malware infection.

Response Workflow

Detection

Use Suricata to identify abnormal traffic patterns

Containment

Isolate infected machine using firewall rules
sudo iptables -A INPUT -s <infected-machine-IP> -j DROP

Eradication

Scan and remove malware using ClamAV
sudo clamscan --remove --recursive /

Recovery

Update system and restore secure state
sudo apt-get update && sudo apt-get upgrade
Key Security Concepts
Incident Response Lifecycle (NIST model)
Detection (IDS / anomaly monitoring)
Containment strategies
Malware eradication techniques
System recovery and patching
Network traffic monitoring
Security Impact

Incident response capabilities are critical in minimizing damage from cyberattacks. Proper execution ensures faster containment, reduced data loss, and improved organizational resilience against malware and intrusion attempts.

Conclusion

This lab demonstrated the full incident response workflow using real-world tools and a malware infection scenario. Understanding roles, structured response phases, and practical tool usage strengthens SOC readiness and improves response effectiveness in real security incidents.
