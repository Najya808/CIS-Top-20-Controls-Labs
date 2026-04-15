Lab 13 — Data Protection Basics
Objective

To understand and implement data protection principles by encrypting files, securing communications with HTTPS and SSH, and validating encryption effectiveness.

Tools & Environment
Windows / Linux (Test VM)
7-Zip
VeraCrypt
Local web server (Apache/Nginx)
OpenSSL
Wireshark
Terminal / Command Line
Task 1 — Encrypt a Test File or Folder
Subtask 1.1: Encrypting Using 7-Zip with AES
Launch 7-Zip.
Navigate to the file/folder to encrypt.
Right-click → 7-Zip > Add to archive…
Configure:
Archive format: .zip or .7z
Encryption method: AES-256
Enter strong password
Click OK to encrypt.

 Result: File/folder encrypted using AES-256.

Subtask 1.2: Encrypting Using VeraCrypt
Open VeraCrypt → Create Volume.
Choose Encrypt a non-system partition/drive.
Select disk/partition or file container.
Set Encryption Algorithm: AES.
Enter strong password → Mount volume.

 Result: Data encrypted and accessible only with correct password.

Task 2 — Configure Secure Communications
Subtask 2.1: Enable HTTPS on Local Web Server
Ensure server software installed (Apache/Nginx).
Generate self-signed SSL certificate:
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout server.key -out server.crt
Configure server to use certificate:

Apache:

<VirtualHost *:443>
  ServerName example.com
  SSLEngine on
  SSLCertificateFile "/path/to/server.crt"
  SSLCertificateKeyFile "/path/to/server.key"
</VirtualHost>

Nginx:

server {
  listen 443 ssl;
  server_name example.com;
  ssl_certificate /path/to/server.crt;
  ssl_certificate_key /path/to/server.key;
}
Restart server to apply changes.

 Result: HTTPS enabled on local server.

Subtask 2.2: Enable SSH Instead of Telnet
Install SSH server:
sudo apt-get install openssh-server
Disable Telnet:
sudo systemctl stop telnet
sudo systemctl disable telnet
Start and enable SSH:
sudo systemctl enable ssh
sudo systemctl start ssh

 Result: SSH enabled; Telnet disabled.

Task 3 — Validate Data Encryption
Subtask 3.1: Inspect Encrypted Files
Capture network traffic with Wireshark.
Access server over HTTPS → observe encrypted TLS traffic.
Attempt opening encrypted file without key → access denied.
Subtask 3.2: Attempt to Open Encrypted File
Without correct password, 7-Zip or VeraCrypt denies access.

 Result: Encryption validated; unauthorized access prevented.

Key Security Concepts Learned
File and folder encryption with AES-256
Secure communication using HTTPS and SSH
Replacing insecure protocols (Telnet → SSH, HTTP → HTTPS)
Validation of encryption and traffic inspection
Enhancing data confidentiality and integrity
Security Impact
Before:
Files stored in plaintext
Communications insecure (HTTP/Telnet)
After:
AES-encrypted files and volumes
HTTPS and SSH secure network communication
Unauthorized access effectively blocked
Conclusion

In this lab, I implemented encryption for files and communications, transitioned from insecure protocols to secure ones, and validated effectiveness using traffic analysis and access testing. These steps reinforce data protection and are fundamental for SOC operations.
