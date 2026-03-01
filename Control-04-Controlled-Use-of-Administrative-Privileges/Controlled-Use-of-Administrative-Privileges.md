Controlled Use of Administrative Privileges Lab

CIS Control 4 – Controlled Use of Administrative Privileges

Objective

This lab focuses on identifying administrative accounts on a Linux system, removing or downgrading unnecessary privileges, and documenting changes to maintain system security and accountability.

Prerequisites

Basic knowledge of Linux system administration

Access to a Linux machine or virtual environment

Familiarity with terminal / command line

Lab Overview

Administrative privileges provide full system control and must be tightly managed. This lab demonstrates how to audit privileged accounts, enforce least privilege principles, and document security changes.

Task 1: Identify Accounts with Administrative Privileges
Step 1: Check Sudo Group
cat /etc/group | grep sudo

For systems using the wheel group:

cat /etc/group | grep wheel
Step 2: Inspect the Sudoers File
sudo visudo

Review user specifications and privilege assignments carefully.

Task 2: Remove or Downgrade Unnecessary Admin Accounts
Step 1: Evaluate Accounts

Determine if each account truly requires administrative access

Apply the principle of least privilege

Step 2: Remove from Sudo Group
sudo deluser <username> sudo

For wheel-based systems:

sudo gpasswd -d <username> wheel
Step 3: Remove Account (If Necessary)
sudo userdel <username>
Step 4: Verify Changes
cat /etc/group | grep sudo
Task 3: Document Changes and Verify Stability
Step 1: Create a Change Log

Example:

[Change Log – 2026-03-01]
Removed administrative privileges from user1 due to policy review.
