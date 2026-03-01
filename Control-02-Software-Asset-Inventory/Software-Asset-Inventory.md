Software Asset Inventory Lab

CIS Control 2 – Inventory and Control of Software Assets

Objective

This lab demonstrates how to inventory installed software on both Windows and Linux systems using command-line tools. The objective is to export software data for analysis and identify unknown or end-of-life (EOL) applications that may pose security risks.

Prerequisites

Basic familiarity with Windows and Linux command line

Access to a Windows machine or VM

Access to a Linux machine or VM

Spreadsheet software (LibreOffice Calc / Google Sheets / Excel)

Lab Overview

Maintaining a software asset inventory helps:

Detect unauthorized applications

Identify outdated or EOL software

Improve vulnerability management

Ensure compliance with security policies

This lab focuses on using native OS tools to collect and analyze installed software data.

Task 1: Inventory Software on Windows
Step 1: Using WMIC

Open Command Prompt as Administrator and execute:

wmic product get name,version,vendor

This lists installed software with version and vendor information.

Step 2: Export to CSV
wmic product get name,version,vendor /format:csv > installed_software.csv

Open the generated CSV file in spreadsheet software for review.

Task 2: Inventory Software on Linux
Debian-Based Systems (dpkg)
dpkg-query -W -f='${binary:Package},${Version},${Maintainer}\n'

Export to CSV:

dpkg-query -W -f='${binary:Package},${Version},${Maintainer}\n' > installed_software.csv
RPM-Based Systems (rpm)
rpm -qa --queryformat '%{NAME},%{VERSION},%{PACKAGER}\n'

Export to CSV:

rpm -qa --queryformat '%{NAME},%{VERSION},%{PACKAGER}\n' > installed_software.csv
Task 3: Identify Unknown or End-of-Life Software
Step 1: Analyze Exported Data

Open the CSV file in spreadsheet software

Review installed applications and versions

Cross-reference versions using official vendor websites or security databases

Step 2: Flag Risky Software

Highlight unknown software

Identify end-of-life (EOL) versions

Document potential risks (e.g., no security patches, unsupported versions)

Results

After completing this lab:

Software inventory was successfully generated for Windows and Linux systems

Data was exported for structured analysis

Unknown or outdated software was identified and flagged

Conclusion

Software asset inventory is critical for maintaining secure and compliant systems. Regular audits of installed applications reduce exposure to vulnerabilities and improve operational security posture.
