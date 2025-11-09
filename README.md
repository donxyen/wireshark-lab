# 🦈 Wireshark Lab

<img width="1531" height="691" alt="x" src="https://github.com/user-attachments/assets/27f1d601-c7ac-4a7d-bd53-46a3feb0415b" />

## 🎯 Objective
This Wireshark Lab is to gain hands-on experience using **Wireshark** to capture, analyze, and interpret network traffic. This project focuses on understanding **packet structures, network protocols, and communication flows** to identify anomalies, suspicious activity, and potential security threats within network data.  

## 🔑 Key Skills
- **Wireshark Configuration & UI Customization** – Create and manage profiles, add custom columns, and tailor layouts for efficient packet analysis.  
- **Traffic Filtering & Display Rules** – Use advanced display filters to isolate specific hosts, protocols, and conversations.  
- **Packet Capture Techniques** – Learn where and how to capture network traffic effectively for different environments.  
- **Understanding Packet Anatomy** – Analyze how encapsulation works across layers (Ethernet, IP, TCP/UDP, Application).  
- **IP Traffic Analysis** – Identify source/destination addresses, TTL, fragmentation, and routing behavior.  
- **UDP & TCP Analysis** – Inspect connectionless vs. connection-oriented protocols, detect handshake anomalies, and identify retransmissions or resets.  
- **Protocol Decoding** – Interpret HTTP, DNS, ARP, ICMP, and TLS traffic to understand network behavior.  
- **Traffic Coloring & Visualization** – Apply color rules and filter buttons to quickly recognize packet types and anomalies.  
- **Network Troubleshooting** – Diagnose latency, dropped packets, and misconfigured services through detailed packet inspection.  
- **Threat Detection Fundamentals** – Recognize signs of scanning, spoofing, DoS, and suspicious payload activity within captured traffic.

## Wireshark Configuration & UI Customization  
<img width="1425" height="744" alt="1" src="https://github.com/user-attachments/assets/6b425a87-2b1c-4531-bd06-5add7c96603c" />

### Configuring Profiles
- Created and customized **Wireshark profiles** to streamline packet analysis workflows.  
- Configured layouts, color rules, and display filters to quickly switch between **network monitoring**, **protocol analysis**, and **threat investigation** views.  
<img width="608" height="374" alt="2" src="https://github.com/user-attachments/assets/e83732e0-215b-45c4-b470-31e15705e8f3" />

### Coloring Profile
- Applied **color rules** in Wireshark to visually distinguish different protocols and packet types.  
- Enhanced traffic visibility by highlighting patterns, anomalies, and potential threats for faster analysis.  
<img width="1550" height="806" alt="3" src="https://github.com/user-attachments/assets/62270015-668d-4561-a08d-9de81c5e494b" />

### Filter Buttons
- Added **custom filter buttons** in Wireshark to quickly apply common display filters.  
- Improved analysis efficiency by enabling one-click access to specific protocols, hosts, or traffic types.  
<img width="1591" height="124" alt="4" src="https://github.com/user-attachments/assets/dc291469-44d3-4dd2-829f-341f413e641f" />

### Multi-Port Filtering
- Used **multi-port filtering** to view network traffic across multiple ports simultaneously
- Simplified packet analysis by isolating related protocols and services within a single filtered view.  

<img width="1269" height="532" alt="5" src="https://github.com/user-attachments/assets/3c1a35f4-9be6-4827-ab44-90c456f33572" />

## Analayzing Packat Captures

### Unicasts VS Broadcasts VS Multicasts
<img width="885" height="678" alt="1" src="https://github.com/user-attachments/assets/c11975b7-4e12-4182-a3a5-941efe991e1c" />

- **Unicast:** One-to-one communication between two MAC addresses.  
  Switch forwards frames based on MAC address table; unknown destinations are flooded.
- **Broadcast:** One-to-all communication (`FF:FF:FF:FF:FF:FF`).  
  Common in **ARP requests** where a host announces, “Who has this IP?”
- **Multicast:** One-to-many communication used by specific protocols (e.g., **STP**, **CDP**, **LLDP**).  
  Wireshark identifies these as `IPv4mcast` frames.

### Understanding IP Header
<img width="906" height="895" alt="2" src="https://github.com/user-attachments/assets/9ded73ff-07e1-4d59-af33-e4c8c07da19f" />

- Analyzed IPv4 header fields in Wireshark to understand how packets are structured and routed. Observed fields like TTL, protocol, and IP identification in live captures, and learned how checksum offloading to NICs can cause false errors during local captures.

## IP Analysis

### TTL Field
<img width="870" height="839" alt="3" src="https://github.com/user-attachments/assets/c006401b-ba98-46a4-b234-1431210fd553" />

- Observed a packet with a TTL value of 57, which indicates it’s approximately **8 router hops away** from the source (assuming an initial TTL of 65).
- Used this to estimate network path distance and confirm normal routing behavior.

### IP Fragmentation
<img width="287" height="212" alt="Connected packet" src="https://github.com/user-attachments/assets/a544be28-2025-4012-bc44-12569376a5e2" />

- Wireshark indicates visual packet fragmentation with the dot and the arrow to show that these packets belong together.

 <img width="327" height="89" alt="more" src="https://github.com/user-attachments/assets/e95ebe51-b80b-4c4f-930f-4411ac21f04e" />
 <img width="408" height="90" alt="nonr" src="https://github.com/user-attachments/assets/b3aaf3d0-f76f-40ed-b33c-4c6283dc65a3" />

- Both packets share the same ID, to show they do belong together
<img width="594" height="99" alt="share" src="https://github.com/user-attachments/assets/d5b16cae-670d-46c9-935a-e44e234ca39a" />

 ## UDP Analysis
 <img width="901" height="431" alt="23" src="https://github.com/user-attachments/assets/b9d8b1d2-7879-4140-a5b8-2f1840598454" />

 - Captured and inspected UDP packets in Wireshark — noted its connectionless nature with minimal headers, making it ideal for fast, lightweight communication like DNS and streaming.

### DHCP
<img width="908" height="488" alt="dhcp" src="https://github.com/user-attachments/assets/a721cf5c-fa8f-4b43-93d1-c1dbae51a1db" />

- Captured the full DHCP handshake in Wireshark — Discover, Offer, Request, and Acknowledge.  
- Observed broadcasts on UDP ports **67 (server)** and **68 (client)**, confirming normal IP lease assignment behavior.

### DNS
<img width="789" height="194" alt="dns" src="https://github.com/user-attachments/assets/89bc10a3-0d73-4da8-b3bd-96bd5c5548f1" />

- Observed hostname-to-IP resolution and verified response times between client and DNS server.









