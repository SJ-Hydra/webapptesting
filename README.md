# Web Application Testing Caveat 
This is just my process for web application testing. There are likely to be items not disclosed in this list. Be sure to carry out the kick-off discussion using the attached questionaire (kick_off_call.txt) prior to commencing the test. Always have written permission from the system owner(s) before conducting penetration tests. 

# Web Application Testing Process
First: System Owner Authorization
First: System Owner Communication Agreement
First: Notify System Owner of Commencement

Recon:
Whois: https://www.whois.net/
Wayback: https://archive.org/web/
Google: "site:<domain>", "site:<domain> AND doctype:<doctype>", GHDB
Jobsearch: Linkedin, Glassdoor, Google Job Search
Social Media: Twitter, Facebook, Instagram
Data Breach: https://haveibeenpwned.com/PwnedWebsites

Active Scanning:
**Automated Tooling:
Port Scan: nmap -Pn <IP>
Port Scan: nmap -Pn -p- -sV <IP>

Nessus: Web Application Test
Nikto: nikto -h <domain>
Directory Bust: dirsearch: https://github.com/maurosoria/dirsearch
Sub-domain Directory Busting: gobuster: https://github.com/OJ/gobuster  (sample command: gobuster dns -d mysite.com -t 50 -w common-names.txt
  SecList: https://github.com/danielmiessler/SecLists
SSL Check: https://www.ssllabs.com/ssltest/
HTTP Sec Headers Check: https://securityheaders.com/

**Manual Checks
Information Disclosure: Verbose HTTP Response Headers
Information Disclosure: Error Pages
Information Disclosure: Document Exif Data
Information Disclosure: Default Content Not Deleted (Apache: index.html..., IIS: ...)
Information Disclosure: robots.txt, sitemap.xls, phpinfo.php

Software: Web Server version
Software: Web Application version
Software: Web Application Framework, Libraries, etc.

Login Portal: Error Message Username Enumeration
Login Portal: Weak Password Policy
Login Portal: Brute Force Protection
Login Portal: Account Lockout

Account Login: Poor password change function
Account Login: Concurrent Login
Account Login: Username Change Function
Account Login: Account Timeout Function

Session Management: Big F5 IP Disclosure
Session Management: JSON Web Token Disclosure
Session Management: Cookie Flags
Session Management: Cookie Expiration
Session Management: Randomness

Field Entry: SQL
Field Entry: XXS: https://github.com/pgaijin66/XSS-Payloads/blob/master/payload.txt
Field Entry: XXE
Field Entry: Other Fuzzing: https://github.com/minimaxir/big-list-of-naughty-strings

API: Misconfigurations
API: Information Disclosure
API: Unprotected Calls

URL String: LFI, RFI
URL String: Predictibility
URL String: Security through obscurity
URL String: CSRF

Other: Clickjacking
Other: Document metadata disclosure
Other: Outright Disclosures
Other: Sensitive data unprotected

Email (for password reset, etc.): SPF Record Check, DMS

Let the application guide you from here, misconfigurations are bound to be around. 

Final: Notify system owner of completion.
