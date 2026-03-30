Lab 12 — Boundary Defense
Objective

To understand and implement network boundary defenses by documenting network architecture, configuring firewall rules, and testing protection against unauthorized access.

Tools & Environment
Ubuntu Linux (Test VM)
UFW (Uncomplicated Firewall)
Terminal
draw.io (Network Diagram Tool)
Task 1 — Document the Network Boundary
Step 1: Create a Network Diagram
Identified key components:
Router
Firewall
Internal devices (PCs, IoT, etc.)
Created a network diagram using draw.io
Example Structure
[Internet] -- [Router] -- [Firewall] -- [Internal Network]
Key Points
Router and firewall act as boundary defense layers
Visualized traffic flow between external and internal network

✅ Result: Network boundary clearly documented.

Task 2 — Verify Inbound and Outbound Firewall Rules
Step 1: List Current Firewall Rules
sudo ufw status verbose
Reviewed allowed and denied traffic rules
Identified exposed/open ports
Step 2: Block Unused Inbound Ports
Blocked unused port (example: 8080)
sudo ufw deny 8080
Verify Rule Applied
sudo ufw status
Confirmed port is marked as DENIED

✅ Result: Unnecessary ports successfully blocked.

Task 3 — Test the Boundary Defense
Step 1: Attempt Unauthorized Access
From external system:
nc -vz <external-ip-address> 8080
Observation
Connection refused / denied

✅ Result: Firewall successfully blocked unauthorized access.

Key Security Concepts Learned
Network boundary defense fundamentals
Firewall rule configuration and validation
Inbound vs outbound traffic control
Basic penetration testing techniques
Importance of minimizing exposed ports
Security Impact
Before:
Potentially unnecessary open ports
Limited visibility of network boundary
After:
Clearly defined network architecture
Unused ports blocked
Unauthorized access attempts prevented
Conclusion

In this lab, I implemented boundary defense by documenting the network, configuring firewall rules, and validating security through controlled attack testing. This strengthens protection against external threats and is a critical component of SOC network security monitoring.
