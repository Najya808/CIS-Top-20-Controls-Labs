Lab 18 — Application Software Security
Objective

Understand common web application vulnerabilities such as SQL Injection and Cross-Site Scripting (XSS), identify them in a vulnerable application, and apply secure coding and static analysis practices to mitigate risks.

Tools & Environment
Docker
DVWA (Damn Vulnerable Web Application)
Web browser (localhost access)
Node.js & npm
ESLint
Code editor (VS Code recommended)
Prerequisites
Basic understanding of web application architecture
Familiarity with HTML, JavaScript, and SQL
Docker installed and running
Admin access for installing tools
Tasks
Task 1 — Identification of Vulnerabilities
Subtask 1.1 — Deploy Sample Vulnerable Web Application (DVWA)

DVWA is a deliberately insecure web application used for security training and testing.

Steps:

docker pull vulnerables/web-dvwa
docker run -d -p 80:80 vulnerables/web-dvwa

Access the application:

http://localhost

Log in and set security level to low for testing purposes.

Subtask 1.2 — Explore Common Web Vulnerabilities
SQL Injection (SQLi)

Description:
SQL Injection occurs when attackers manipulate SQL queries by injecting malicious input into database queries.

Test Example (DVWA SQLi module):

1' OR '1'='1

Observation:

Application returns unintended database records
Authentication or query logic is bypassed
Cross-Site Scripting (XSS)

Description:
XSS allows attackers to inject malicious JavaScript into web pages viewed by other users.

Test Example (Reflected XSS):

<script>alert('XSS Vulnerability!')</script>

Observation:

Script executes in browser context
Confirms lack of proper input sanitization
Task 2 — Static Analysis Tools
Subtask 2.1 — Install ESLint (Static Code Analysis)

ESLint helps detect insecure coding patterns and enforce secure development standards.

Installation:

npm install -g eslint

Run analysis on a JavaScript file:

eslint vulnerableScript.js

Output Analysis:

Identifies unused variables
Flags unsafe coding practices
Highlights potential injection risks
Subtask 2.2 — Security-Focused Linting Configuration

Example ESLint security rule configuration:

{
  "rules": {
    "security/detect-possible-timing-attacks": "warn"
  }
}

Security Value:

Helps detect unsafe code patterns early in development
Reduces risk of introducing XSS or injection vulnerabilities
Enforces secure coding discipline in CI/CD pipelines
Task 3 — Secure Coding Practices
Subtask 3.1 — SQL Injection Mitigation
❌ Vulnerable Approach:
"SELECT * FROM users WHERE id = " + userId;
✅ Secure Approach (Prepared Statements):
connection.query(
  'SELECT * FROM users WHERE id = ?',
  [userId],
  function(error, results) {
    // handle results safely
  }
);

Security Benefit:

Separates code from data
Prevents malicious SQL injection payload execution
Enforces query parameterization
XSS Protection
❌ Vulnerable Approach:

Directly inserting user input into DOM

✅ Secure Approach (Input Sanitization):
const clean = DOMPurify.sanitize(userInput);
document.getElementById("output").innerHTML = clean;

Security Benefit:

Removes malicious scripts
Prevents execution of injected JavaScript
Protects client-side integrity
Key Security Concepts
SQL Injection (SQLi)
Cross-Site Scripting (XSS)
Input validation & sanitization
Static Application Security Testing (SAST)
Secure coding principles
Parameterized queries
Security Impact

Application vulnerabilities are one of the most common attack vectors in real-world breaches. Identifying and mitigating these flaws significantly reduces risks such as:

Data theft
Account compromise
Remote code execution
Session hijacking
Conclusion

This lab demonstrated how insecure web applications can be exploited through SQL Injection and XSS, and how static analysis tools and secure coding practices help mitigate these risks. Implementing parameterized queries and input sanitization is essential for building secure applications in production environments.
