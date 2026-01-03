# Task 8 – Capture Network Traffic with Wireshark

For this task, I captured and analyzed network traffic using Wireshark.
The objective was to observe different types of network packets and understand how data flows across a network.

---

## 1. Objective

The main objective of this task was to learn how to capture live network traffic and analyze commonly used protocols such as TCP, DNS, and HTTP using Wireshark.

---

## 2. Environment and Tools Used

* Operating System: Kali Linux (VirtualBox)
* Network Interface: eth0
* Tool Used: Wireshark

The eth0 interface was used because the system was running inside a VirtualBox environment.

---

## 3. Traffic Capture Setup

Wireshark was launched and network traffic capture was started on the eth0 interface.

### Start Wireshark

```bash
wireshark
```

Normal browsing activity was performed during the capture to generate network traffic.

---

## 4. Traffic Analysis Using Filters

After capturing traffic, display filters were applied to analyze specific types of packets.

### TCP Traffic Analysis

Filter used:

```
tcp
```

TCP packets showed normal connection establishment and termination, indicating reliable communication between systems.

---

### DNS Traffic Analysis

Filter used:

```
dns
```

DNS packets revealed domain name resolution requests, which occur when websites are accessed.

---

### HTTP Traffic Analysis

Filter used:

```
http
```

HTTP packets displayed unencrypted web requests and responses, meaning the data was transmitted in plain text.

---

## 5. Observations

* Multiple network protocols were observed during the capture.
* HTTP traffic was not encrypted.
* DNS traffic exposed domain resolution activity.
* TCP traffic demonstrated standard communication behavior.

---

## 6. Files Included

* **wireshark_capture.pcap / wireshark_capture.pcapng** – Saved network traffic capture file
* **Screenshots/** – Capture start, filters applied, and packet analysis
* **How to Capture Network Traffic with Wireshark.mp4** – Screen recording of the traffic capture and analysis
* **README.md** – Documentation explaining the capture and analysis

---

## 7. Conclusion

This task demonstrated how Wireshark can be used to capture and analyze network traffic.
By observing TCP, DNS, and HTTP packets, I gained a better understanding of how network communication works and why traffic monitoring is important for network security.
