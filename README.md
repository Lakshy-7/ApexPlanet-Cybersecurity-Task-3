ApexPlanet Cybersecurity & Ethical Hacking Internship — Task 3

Web Application Security

Scope

All practical testing was performed against the intentionally vulnerable DVWA application running locally on 127.0.0.1.

Completed Areas
SQL Injection — normal input and basic injection demonstration
Reflected XSS
Stored XSS
CSRF password-change exercise
Burp Suite — Intercept, Repeater and Intruder workflow
File Inclusion / Local File Inclusion (LFI)
RFI limitation documented because PHP allow_url_include was disabled
Security Headers analysis
Apache Security Headers configuration and local verification
Attack Scenarios & Mitigations
1. SQL Injection
Scenario: User-controlled input was able to influence the SQL query in the intentionally vulnerable DVWA application.

Mitigation: Use prepared/parameterized statements, validate input, and never construct SQL statements by concatenating untrusted input.

2. Reflected XSS
Scenario: Crafted input was reflected by the application and produced browser-side script execution in the lab.

Mitigation: Context-aware output encoding, input validation, and an appropriate Content Security Policy (CSP).

3. Stored XSS
Scenario: Input stored by the application was later rendered in the page and produced browser-side script execution in the lab.

Mitigation: Validate and encode stored data before rendering; use CSP as an additional defense.

4. CSRF
Scenario: The DVWA password-change functionality was tested in the local lab.

Mitigation: Use unpredictable, server-side validated CSRF tokens for state-changing requests and appropriate cookie protections.

5. File Inclusion / LFI
Scenario: Local File Inclusion behavior was demonstrated in DVWA.

Mitigation: Use an allowlist of permitted files, avoid user-controlled filesystem paths, and canonicalize/validate paths.

RFI limitation: Remote File Inclusion was not demonstrated because allow_url_include was disabled in the lab PHP configuration. This is documented as a limitation rather than claiming an RFI result.

6. Burp Suite Advanced
Burp Suite was used to intercept a local web request, send it to Repeater, and send a request to Intruder for testing.

7. Web Security Headers
A test-site header analysis was reviewed using SecurityHeaders. Appropriate response headers were then configured in local Apache and verified locally.

Headers configured:

X-Content-Type-Options: nosniff
X-Frame-Options: SAMEORIGIN
Referrer-Policy: strict-origin-when-cross-origin
Permissions-Policy: geolocation=(), microphone=(), camera=()
Evidence
The accompanying screenshots document the practical work:

DVWA Dashboard
SQLi normal input
SQLi injection
Reflected XSS
Stored XSS
CSRF result
Burp intercepted request
Burp Repeater
Burp Intruder
File Inclusion page
LFI result
Security Headers analysis
Apache Security Headers fix

Ethical Use
These exercises were performed only in an intentionally vulnerable local training environment. Do not test systems without authorization.
## 🎥 Task 3 Demo Video

### LinkedIn Video
[Watch the complete Task 3 demonstration on LinkedIn](YOUR_LINKEDIN_POST_LINK)

### Video File
[ApexPlanet Task 3 Demo Video](https://github.com/Lakshy-7/ApexPlanet-Cybersecurity-Task-3/blob/main/Task3_Demo_GitHub_Under25MB.mp4)
