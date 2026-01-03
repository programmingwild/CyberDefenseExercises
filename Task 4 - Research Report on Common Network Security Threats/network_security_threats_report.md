# Task 4 – Research Report on Common Network Security Threats

## 1. Introduction
Modern computer networks face a wide range of security threats that continue to increase in complexity and frequency. As organizations rely heavily on interconnected devices and online services, even a small vulnerability can lead to major disruptions.  
This report discusses three major network security threats: **DoS/DDoS attacks**, **Man-in-the-Middle (MITM) attacks**, and **spoofing attacks**. It explains how each threat works, provides real-world examples, and outlines preventive measures.

---

## 2. DoS and DDoS Attacks

### 2.1 What Is a DoS/DDoS Attack?
A **Denial of Service (DoS)** attack attempts to overwhelm a system, service, or network with excessive traffic, making it unavailable to legitimate users.  
A **Distributed Denial of Service (DDoS)** attack uses multiple compromised systems (botnets) to generate a much larger traffic flood toward the target.

### 2.2 How It Works
Common methods include:
- **SYN Flood** – exploiting the TCP handshake
- **UDP Flood** – sending random UDP packets to overload resources
- **HTTP Flood** – sending fake web requests
- **Amplification Attacks** – using vulnerable servers to multiply attack traffic

### 2.3 Real-World Example
**GitHub Attack (2018):**  
GitHub suffered a record-breaking **1.35 Tbps DDoS attack** through Memcached amplification, causing temporary outages despite strong protection.

### 2.4 Impact
- Website or service downtime  
- Lost revenue and productivity  
- Increased server and bandwidth costs  
- Damaged reputation  
- Possible security breaches during the disruption

### 2.5 Mitigation
- Rate limiting and traffic filtering  
- Cloud-based DDoS protection (Cloudflare, Akamai, AWS Shield)  
- SYN cookies to prevent SYN floods  
- Traffic monitoring and anomaly detection  
- Distributed and redundant infrastructure

---

## 3. Man-in-the-Middle (MITM) Attacks

### 3.1 What Is a MITM Attack?
A **Man-in-the-Middle attack** occurs when an attacker secretly intercepts and possibly alters communication between two parties.  
The victims believe they are communicating directly, but the attacker is positioned between them.

### 3.2 How It Works
MITM attacks are commonly performed using:
- **ARP Spoofing** – poisoning the ARP table to redirect traffic  
- **DNS Spoofing** – sending victims to malicious websites  
- **Rogue Wi-Fi Access Points** – tricking users into unsafe networks  
- **SSL Stripping** – downgrading HTTPS to HTTP

### 3.3 Real-World Example
**Superfish Incident (2015):**  
Lenovo laptops shipped with software that intercepted HTTPS traffic, unintentionally creating MITM vulnerabilities for millions of users.

### 3.4 Impact
- Theft of login credentials  
- Session hijacking  
- Exposure of sensitive data  
- Malware injection into network traffic  
- Compromised integrity and confidentiality

### 3.5 Mitigation
- Avoid public Wi-Fi or use VPN services  
- Enforce HTTPS and use modern TLS versions  
- Enable DNSSEC  
- Enable Dynamic ARP Inspection and DHCP snooping  
- Educate users about safe network practices

---

## 4. Spoofing Attacks

### 4.1 What Is Spoofing?
Spoofing occurs when an attacker impersonates another device or user by falsifying identity information such as IP address, MAC address, DNS responses, or email headers.

### Common Types of Spoofing
- **IP Spoofing**  
- **ARP Spoofing**  
- **DNS Spoofing**  
- **Email Spoofing**

### 4.2 How It Works
Attackers typically:
- Forge packet headers  
- Send fake ARP responses  
- Redirect traffic using DNS cache poisoning  
- Send emails pretending to be trusted senders

### 4.3 Real-World Example
**Kaminsky DNS Vulnerability (2008):**  
A major flaw allowed attackers to poison DNS caches, redirecting users to fake and malicious websites.

### 4.4 Impact
- Unauthorized access to systems  
- Opening the door for MITM attacks  
- Traffic redirection without detection  
- Credential theft and phishing  
- Malware distribution

### 4.5 Mitigation
- Use DNSSEC for secure DNS responses  
- Configure SPF, DKIM, and DMARC for email protection  
- Implement Dynamic ARP Inspection  
- Use static ARP entries for critical devices  
- Monitor DNS and ARP traffic regularly

---

## 5. Why These Threats Still Matter
These attacks remain common because:
- Attack tools are easy to find and use  
- Many networks still use outdated security configurations  
- IoT devices greatly expand the attack surface  
- Remote work increases exposure to unsafe networks

Organizations that fail to address these threats face:
- Data breaches  
- Financial losses  
- Service downtime  
- Legal consequences  
- Loss of customer trust

---

## 6. Conclusion
DoS/DDoS, MITM, and spoofing attacks continue to be major threats to modern networks. Understanding how these attacks work and applying strong preventive measures—such as encryption, secure DNS, proper network segmentation, and robust monitoring—helps organizations significantly reduce their risk.  
By staying aware of these threats and implementing layered security controls, networks can remain resilient and better prepared for real-world cyberattacks.
