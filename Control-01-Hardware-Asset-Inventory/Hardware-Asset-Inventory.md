Hardware Asset Inventory Lab

CIS Control 1 – Inventory and Control of Enterprise Assets

Objective

This lab focuses on implementing a basic hardware asset inventory system and validating it using network scanning techniques. The goal is to ensure visibility and accountability of all hardware assets within a network environment.

Prerequisites

Basic understanding of networking and hardware components

Familiarity with command-line interface

Access to a local network

nmap installed

Lab Overview

Maintaining an accurate hardware inventory is critical for:

Security visibility

Detecting unauthorized devices

Asset lifecycle management

Compliance with security frameworks

This lab demonstrates how to document assets and validate them using a network scan.

Task 1: Create Hardware Asset List
Step 1: Identify Devices

List all hardware assets such as:

Desktop PCs

Laptops

Routers

Switches

Use structured documentation:

Asset ID	Asset Type	Model	Serial Number	Location	Owner
PC001	Desktop	Dell OptiPlex	SN12345	Office	IT
RT001	Router	TP-Link	SN56789	Server Room	Network Team
Step 2: Assign Ownership

Assign a unique Asset ID

Define responsible department or individual

Label devices clearly

Task 2: Validate Inventory with Network Scan
Install Nmap (if needed)
sudo apt update
sudo apt install nmap
Perform Network Scan
nmap -sn 192.168.1.0/24

Replace with your local network range.

Validate Results

Compare scan output with inventory list

Identify missing or unauthorized devices

Update inventory accordingly

Results

After completing this lab:

A structured hardware inventory was created

Asset ownership was defined

Devices were validated using network scanning

Conclusion

Hardware asset inventory is foundational to enterprise security. Continuous monitoring and periodic network scans ensure visibility, accountability, and compliance with best security practices.
