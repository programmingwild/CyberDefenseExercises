# Network Security Assessment Report

## 1. Introduction

This report presents a network security assessment conducted on a local test environment. The purpose of this assessment is to identify open ports, running services, and observable network traffic in order to understand potential security risks. The assessment uses previously captured Nmap scan results and Wireshark network traffic captures.

---

## 2. Assessment Scope

* Target Environment: Local test system
* Network Type: Local / VirtualBox-based network
* Tools Used:

  * Nmap (for network scanning and service enumeration)
  * Wireshark (for network traffic capture and analysis)

The assessment was performed only on authorized systems for learning and analysis purposes.

---

## 3. Nmap Scan Analysis

### 3.1 Scan Overview

Nmap was used to scan the target system to identify open ports, running services, and operating system details. The scan results were saved in the file `nmap_results.txt` and analyzed as part of this report.

### 3.2 Open Ports Identified

The scan identified the following open ports:

| Port     | Service | Description                                    |
| -------- | ------- | ---------------------------------------------- |
| 22/tcp   | SSH     | Secure Shell service for remote administration |
| 8000/tcp | HTTP    | Python Simple HTTP Server used for testing     |

### 3.3 Security Observations

* Most of the scanned ports were closed, which reduces the system’s overall attack surface.
* Port 22 (SSH) is commonly targeted for brute-force attacks if weak credentials are used.
* Port 8000 was running an HTTP service with directory listing enabled, which can expose files and data.

---

## 4. Wireshark Traffic Analysis

### 4.1 Capture Details

Network traffic was captured using Wireshark on the `eth0` interface, which is the default network interface in a VirtualBox environment. The captured traffic was saved as `wireshark_capture.pcap`.

### 4.2 Protocols Observed

The following protocols were observed during the traffic analysis:

* TCP
* DNS
* HTTP

### 4.3 Traffic Analysis Findings

* **TCP Traffic**: TCP packets showed normal connection establishment and termination, indicating reliable communication between systems.
* **DNS Traffic**: DNS packets revealed domain name resolution activity whenever websites were accessed.
* **HTTP Traffic**: HTTP packets showed unencrypted requests and responses, meaning data was transmitted in plain text.

---

## 5. Identified Security Risks

Based on the analysis, the following security risks were identified:

* Exposure of services through open ports can provide entry points for attackers.
* SSH services may be vulnerable to brute-force attacks if not properly secured.
* Unencrypted HTTP traffic can be intercepted on the network.
* Directory listing on HTTP services may expose sensitive files.

---

## 6. Recommendations

To improve the network security posture, the following recommendations are suggested:

* Close unused or unnecessary ports.
* Secure SSH using strong passwords or key-based authentication.
* Disable testing services such as Simple HTTP Server when not required.
* Use HTTPS instead of HTTP to encrypt network traffic.
* Regularly monitor network traffic for suspicious activity.

---

## 7. Conclusion

This network security assessment demonstrated how basic tools such as Nmap and Wireshark can be used to identify potential security weaknesses. While the system had a limited number of open ports, exposed services and unencrypted traffic present potential risks. Applying basic security hardening practices can significantly enhance overall network security.
