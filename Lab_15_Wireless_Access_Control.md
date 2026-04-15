Lab 15 — Wireless Access Control
Objective

To secure a wireless network by configuring strong encryption, disabling insecure features, and validating that only authorized users can connect.

Tools & Environment
Wireless Router (Home/Lab)
Web Browser
Test Devices (Authorized & Unauthorized)
Task 1 — Access Router Admin Panel
Step 1: Connect to Network
Connected system to target Wi-Fi network
Step 2: Open Admin Page
Entered router IP in browser:
192.168.1.1

(or 192.168.0.1 depending on router)

Step 3: Authenticate
Logged in using admin credentials

✅ Result: Access to router configuration panel obtained.

Task 2 — Enable WPA2/WPA3 Encryption
Step 1: Navigate to Wireless Settings
Opened Wireless / WiFi Settings
Step 2: Configure Security Mode
Selected:
WPA2-PSK (AES) or
WPA3-SAE
Step 3: Set Strong Password
Configured strong passphrase (12+ characters)
Step 4: Save Settings
Applied configuration changes

✅ Result: Wireless network secured with strong encryption.

Task 3 — Disable WPS
Step 1: Locate WPS Settings
Found under Wireless / Advanced Settings
Step 2: Disable WPS
Set WPS to Disabled
Step 3: Save Changes
Applied updated configuration

✅ Result: WPS disabled, reducing attack surface.

Task 4 — Validate Access Control
Step 1: Disconnect Device
Disconnected authorized device
Step 2: Attempt Unauthorized Access
Tried connecting without password
Connection failed
Step 3: Reconnect Authorized Device
Connected using correct passphrase
Access successful

✅ Result: Unauthorized access blocked; authorized access verified.

Key Security Concepts Learned
Wireless access control mechanisms
WPA2/WPA3 encryption standards
Risks of WPS (Wi-Fi Protected Setup)
Strong authentication practices
Preventing unauthorized network access
Security Impact
Before:
Weak or no encryption
WPS enabled (security risk)
Higher risk of unauthorized access
After:
Strong WPA2/WPA3 encryption enforced
WPS disabled
Unauthorized users prevented from connecting
Conclusion

In this lab, I secured a wireless network by enabling strong encryption, disabling insecure features like WPS, and validating access controls. These steps significantly reduce the risk of unauthorized access and strengthen overall network security.
