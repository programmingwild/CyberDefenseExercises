# Task 1 – Basic Network Scanning Using Nmap

For this task, I performed a basic network scan on my Kali Linux machine using Nmap.  
The goal was to identify open ports, running services, and general system information.

---

## 1. System Scanned
Target IP: 192.168.0.112  
This is the IP address of my Kali Linux VM on bridged mode.

---

## 2. Commands Used

### Basic host scan
nmap 192.168.0.112

### Service and version scan
nmap -sV 192.168.0.112

### Aggressive scan (OS, service versions, scripts)
nmap -A 192.168.0.112

I saved the aggressive scan output using:
nmap -A 192.168.0.112 -oN nmap_scan_results.txt

---

## 3. Scan Results Summary

Nmap detected two open ports on my system:

### • Port 22/tcp – SSH
- Service: OpenSSH 10.0p2 Debian  
- This is the secure shell service used for remote login.
- I started the SSH service manually before scanning, which is why this port appeared open.

### • Port 8000/tcp – HTTP (Python SimpleHTTPServer)
- Service: SimpleHTTPServer 0.6 (Python 3.13.7)
- I started a temporary Python web server for testing.
- Nmap also detected the server header and the default directory listing.

Other observations:
- 998 ports were closed, which is normal since the system had no other services running.
- OS detection suggested Linux kernel versions between 2.6.x and 6.x, which is expected for Kali Linux.
- Network distance was 0 hops because I scanned my own machine.

---
## 4. Findings and Significance of Open Ports

From the scan, two ports were open on my system: 22/tcp and 8000/tcp.  
Below is a short explanation of what they are used for and why they matter in security.

### 1. Port 22/tcp – SSH (OpenSSH 10.0p2)
Port 22 is used for SSH, which allows secure remote logins into a machine.  
It uses encryption, so data and passwords are protected when someone connects.

Security significance:
- If SSH is exposed on a network, attackers often try brute-force login attempts.
- It’s important to use strong passwords or SSH keys.
- This is a normal open port on Linux systems since SSH is commonly used for administration.

### 2. Port 8000/tcp – HTTP (Python SimpleHTTPServer)
Port 8000 was open because I started a temporary Python SimpleHTTPServer for testing.  
This server shares files over HTTP and shows a directory listing in the browser.

Security significance:
- SimpleHTTPServer does not provide authentication or security features.
- Anyone on the network could access the shared files if this port is open.
- This type of server should only be used for local development or testing, not in production.

### Overall Summary
Both open ports were expected:
- SSH was intentionally enabled.
- The HTTP service on port 8000 was started manually.

All other scanned ports were closed, which means no unnecessary services were running on the system. This lowers the attack surface and is generally good security practice.

---

## 5. Files Included
- **nmap_scan_results.txt** – Full output from the aggressive Nmap scan.
- **Screenshots/** – Includes Nmap version check, IP address, basic scan, version scan, and aggressive scan.
- **Task 1 Demo Video.mp4** – Shows the commands being executed.
- **README.md** – Explanation of the task and configuration steps.

---

## 6. Conclusion
This task helped me understand how different Nmap scan types work and how to read the results.  
I was able to identify open ports, the services running on those ports, and the operating system information of my system.  
Overall, the task gave me a better idea of how Nmap is used in real network security assessments.

