# CYBER-SECURITY-INTERNSHIP-TASK

1.Find your local IP range (e.g., 192.168.1.0/24).
the local IP address and subnet were identified to determine the correct IP range for scanning. This was done using the following commands:

2.Performing a TCP SYN Scan
 3. nmap -sS 192.168.1.0/24
4. Recording IP Addresses and Open Ports

-23/tcp 
-53/tcp open 
80/tcp open 
5000/tcp open
9000/tcp open 
5.Research common services running on those ports:
Open TCP Ports and Typical Services
Port 23/tcp – Telnet

Service: Telnet

Use: Remote command-line interface.

Security Risk:

Unencrypted communication – credentials and data are sent in plaintext.

Vulnerable to MITM (Man-in-the-middle) attacks.

Often used by attackers to gain unauthorized access if default credentials are present.

Port 53/tcp – DNS

Service: Domain Name System (TCP used for large queries like zone transfers).

Use: Resolving domain names, zone transfers.

Security Risk:

Zone transfer exposure can leak internal network information.

DNS amplification attacks or spoofing if misconfigured.

Should be limited to trusted IPs only.

Port 80/tcp – HTTP

Service: HyperText Transfer Protocol

Use: Web traffic (unencrypted)

Security Risk:

Susceptible to MITM, XSS, SQL injection, and other web-based attacks.

No encryption, so sensitive info can be intercepted.

Should ideally redirect to HTTPS (port 443).

Port 5000/tcp – Python Flask Development Server (common)

Service: Often used for Flask, Web API, or custom web apps.

Use: Local or web application interface.

Security Risk:

Development servers often lack authentication or encryption.

May expose sensitive debugging information.

Should never be exposed to the public in production.

Port 9000/tcp – SonarQube / PHP-FPM / Custom apps

Service: Depends on context (e.g., SonarQube, Dev tools, Docker UI, etc.)

Use: Web interfaces, analytics, debugging.

Security Risk:

May expose administrative interfaces.

Often lack proper authentication or access controls.

Attackers can exploit poorly configured web apps on this port.

# Security Risks from Open Ports
Increased Attack Surface: More open ports mean more potential entry points for attackers.

Unpatched Services: If services on these ports are outdated or unpatched, they can be exploited.

Information Disclosure: Some ports (e.g., Telnet or DNS) may leak information about your system or network.

Unauthorized Access: Misconfigured services may allow access without authentication.

Weak Authentication or Defaults: Ports running services with default credentials are highly vulnerable.



