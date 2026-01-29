# 🌐 Computer Networks - Comprehensive Lab Repository

<p align="center">
  <img src="./images/banner.png" alt="Computer Networks" width="550"/>
</p>

<div align="center">

![Network Banner](https://img.shields.io/badge/Computer-Networks-blue?style=for-the-badge)
![Cisco Packet Tracer](https://img.shields.io/badge/Cisco-Packet_Tracer-1BA0D7?style=for-the-badge&logo=cisco)
![Semester](https://img.shields.io/badge/Semester-3-orange?style=for-the-badge)

**A complete collection of networking concepts, configurations, and practical implementations**

</div>

---

## 📋 Table of Contents

- [About This Repository](#-about-this-repository)
- [Learning Path](#-learning-path)
- [Topics Covered](#-topics-covered)
- [Repository Structure](#-repository-structure)
- [How to Use](#-how-to-use)
- [Study Approach](#-study-approach)
- [Navigation Tips](#-navigation-tips)
- [Tools & Technologies](#-tools--technologies)
- [Prerequisites](#-prerequisites)
- [Connect With Me](#-connect-with-me)

---

## 🎯 About This Repository

This repository contains my comprehensive learning journey through Computer Networks in my 3rd semester. Each topic includes:

- ✅ Detailed theoretical concepts
- ✅ Step-by-step lab configurations
- ✅ Cisco Packet Tracer implementations
- ✅ Troubleshooting guides
- ✅ Best practices and security considerations

**📊 Progress Tracking:** This repository showcases my learning process and hands-on experience.  
**🎓 Project Outputs:** Final projects and implementation results are shared here [Network Engineering Projects Portfolio](Projects/README.md).

---

## 🗺️ Learning Path

The topics are organized in a pedagogical sequence, building from fundamental concepts to advanced implementations:

### **Phase 1: Foundation & Segmentation**
1. **Network Fundamentals** → [Servers](#01-servers)
2. **Network Division** → [Subnetting](#02-subnetting)
3. **Traffic Isolation** → [VLAN](#03-vlan)

### **Phase 2: Switching & Layer 2**
4. **Loop Prevention** → [STP](#04-stp)
5. **Link Aggregation** → [EtherChannel (LACP/PAgP)](#05-etherchannel)
6. **Home Connectivity** → [Home Router](#06-home-router)

### **Phase 3: Security Fundamentals**
7. **Port Protection** → [Port Security](#07-port-security)
8. **VLAN Attacks** → [VLAN Security](#08-vlan-security)
9. **DHCP Protection** → [DHCP Snooping](#09-dhcp-snooping)

### **Phase 4: Routing Foundations**
10. **Routing Concepts** → [Link State & Distance Vector](#10-link-state--distance-vector)
11. **Routing Algorithms** → [Dijkstra & Bellman-Ford](#11-dijkstra--bellman-ford)
12. **Routing Protocols** → [Static, RIP, OSPF, BGP](#12-routing-protocols)

### **Phase 5: Address Translation & WAN**
13. **Address Translation** → [NAT/PAT](#13-natpat)
14. **WAN Connectivity** → [PPP](#14-ppp)
15. **Tunneling** → [GRE Tunneling](#15-gre-tunneling)
16. **Secure Tunneling** → [VPN (IPSec)](#16-vpn-ipsec)

### **Phase 6: Advanced Services**
17. **Wireless Networks** → [WLAN](#17-wlan)
18. **Voice Services** → [VoIP](#18-voip)
19. **High Availability** → [HSRP](#19-hsrp)

### **Phase 7: Security & Access Control**
20. **Network Security** → [Firewall](#20-firewall)
21. **Access Lists** → [ACL](#21-acl)
22. **Remote Access** → [SSH & Telnet](#22-ssh--telnet)

---

## 📚 Topics Covered

Click on any topic to navigate to its detailed documentation:

### 01. [Servers](./01-Servers/README.md)
**Foundation Services**
- DNS Server
- DHCP Server
- HTTP Server
- FTP Server
- Email Server
- Syslog Server
- NTP Server
- AAA Server (RADIUS/TACACS+)

---

### 02. [Subnetting](./02-Subnetting/README.md)
**Network Segmentation**
- FLSM (Fixed Length Subnet Masking)
- VLSM (Variable Length Subnet Masking)
- IP Address Planning
- Subnet Calculations

---

### 03. [VLAN](./03-VLAN/README.md)
**Virtual LANs**
- VLAN Configuration
- Switch-to-Switch Communication
- Router-on-a-Stick
- Layer 3 Switch Configuration
- Inter-VLAN Routing

---

### 04. [STP](./04-STP/README.md)
**Spanning Tree Protocol**
- STP Fundamentals
- Loop Prevention
- Root Bridge Election
- Port States and Roles

---

### 05. [EtherChannel](./05-EtherChannel/README.md)
**Link Aggregation**
- LACP (Link Aggregation Control Protocol)
- PAgP (Port Aggregation Protocol)
- Manual Configuration
- Load Balancing

---

### 06. [Home Router](./06-Home-Router/README.md)
**SOHO Networking**
- Home Router Setup
- NAT Configuration
- Wireless Configuration
- Basic Security Settings

---

### 07. [Port Security](./07-Port-Security/README.md)
**Switch Port Protection**
- MAC Address Limiting
- Violation Modes
- Sticky MAC Addresses
- Unused Port Security

---

### 08. [VLAN Security](./08-VLAN-Security/README.md)
**VLAN Attack Prevention**
- CDP (Cisco Discovery Protocol) Security
- VLAN Hopping Attacks
- Double Tagging Prevention
- Switch Spoofing Protection

---

### 09. [DHCP Snooping](./09-DHCP-Snooping/README.md)
**DHCP Security**
- Rogue DHCP Server Prevention
- DHCP Snooping Database
- Trusted vs Untrusted Ports
- Rate Limiting

---

### 10. [Link State & Distance Vector](./10-Link-State-Distance-Vector/README.md)
**Routing Protocol Categories**
- Link State Protocols
- Distance Vector Protocols
- Comparison and Use Cases
- Convergence Analysis

---

### 11. [Dijkstra & Bellman-Ford](./11-Dijkstra-Bellman-Ford/README.md)
**Routing Algorithms**
- Dijkstra's Algorithm (OSPF)
- Bellman-Ford Algorithm (RIP)
- Shortest Path Calculation
- Algorithm Comparison

---

### 12. [Routing Protocols](./12-Routing-Protocols/README.md)
**Dynamic & Static Routing**
- Static Routing
- RIP (Routing Information Protocol)
- OSPF (Open Shortest Path First)
- BGP (Border Gateway Protocol)
- Dynamic Routing Implementation

---

### 13. [NAT/PAT](./13-NAT-PAT/README.md)
**Network Address Translation**
- Static NAT
- Dynamic NAT
- PAT (Port Address Translation)
- NAT Overload

---

### 14. [PPP](./14-PPP/README.md)
**Point-to-Point Protocol**
- PPP Configuration
- Authentication (PAP/CHAP)
- WAN Connectivity
- Serial Link Configuration

---

### 15. [GRE Tunneling](./15-GRE-Tunneling/README.md)
**Generic Routing Encapsulation**
- GRE Tunnel Configuration
- Multiprotocol Support
- Tunnel Interfaces
- Routing over Tunnels

---

### 16. [VPN (IPSec)](./16-VPN-IPSec/README.md)
**Virtual Private Networks**
- IPSec VPN Configuration
- Site-to-Site VPN
- Encryption & Authentication
- Tunnel Mode vs Transport Mode

---

### 17. [WLAN](./17-WLAN/README.md)
**Wireless Local Area Networks**
- Access Point Configuration
- WLC (Wireless LAN Controller) - Method 1
- WLC (Wireless LAN Controller) - Method 2
- Wireless Security (WPA/WPA2)
- Connecting Laptops, PCs, Smartphones

---

### 18. [VoIP](./18-VoIP/README.md)
**Voice over IP**
- VoIP Configuration
- Call Manager Express
- Dial Plans
- Phone Registration
- Voice VLANs

---

### 19. [HSRP](./19-HSRP/README.md)
**Hot Standby Router Protocol**
- First Hop Redundancy
- Virtual IP Configuration
- Active/Standby Routers
- Priority and Preemption

---

### 20. [Firewall](./20-Firewall/README.md)
**Network Security**
- Firewall Configuration
- Zone-Based Firewall
- Security Policies
- Traffic Filtering

---

### 21. [ACL](./21-ACL/README.md)
**Access Control Lists**
- Standard ACL
- Extended ACL
- Named ACL
- ACL Placement

---

### 22. [SSH & Telnet](./22-SSH-Telnet/README.md)
**Remote Access**
- SSH Configuration (Secure)
- Telnet Configuration
- VTY Line Security
- Authentication Methods

---

## 📁 Repository Structure

```
computer-networks/
│
├── README.md (This file)
├── images/
│   └── banner.png
│
├── 01-Servers/
│   └── README.md
│
├── 02-Subnetting/
│   └── README.md
│
├── 03-VLAN/
│   └── README.md
│
├── 04-STP/
│   └── README.md
│
├── 05-EtherChannel/
│   └── README.md
│
├── 06-Home-Router/
│   └── README.md
│
├── 07-Port-Security/
│   └── README.md
│
├── 08-VLAN-Security/
│   └── README.md
│
├── 09-DHCP-Snooping/
│   └── README.md
│
├── 10-Link-State-Distance-Vector/
│   └── README.md
│
├── 11-Dijkstra-Bellman-Ford/
│   └── README.md
│
├── 12-Routing-Protocols/
│   └── README.md
│
├── 13-NAT-PAT/
│   └── README.md
│
├── 14-PPP/
│   └── README.md
│
├── 15-GRE-Tunneling/
│   └── README.md
│
├── 16-VPN-IPSec/
│   └── README.md
│
├── 17-WLAN/
│   └── README.md
│
├── 18-VoIP/
│   └── README.md
│
├── 19-HSRP/
│   └── README.md
│
├── 20-Firewall/
│   └── README.md
│
├── 21-ACL/
│   └── README.md
│
└── 22-SSH-Telnet/
    └── README.md
```

---

## 🚀 How to Use

### For Learning:
1. **Follow the Learning Path**: Start from Phase 1 and progress sequentially
2. **Explore Topics**: Click on any topic to view detailed documentation
3. **Hands-on Practice**: Download Cisco Packet Tracer files and practice configurations
4. **Review Concepts**: Each README contains theory, commands, and troubleshooting tips

### For Recruiters/Professionals:
- **GitHub**: View my learning process, configurations, and progression
- **LinkedIn**: See completed projects, implementations, and final outputs
- Navigate easily using the clickable topics above

---

## 📖 Study Approach

This repository follows a structured learning path:

1. **Conceptual Understanding** - High-level concepts and terminology
2. **Technical Details** - Implementation specifics and protocols
3. **Practical Applications** - Real-world examples and configurations
4. **Troubleshooting** - Common issues and solutions

---

## 🧭 Navigation Tips

- Each topic has its own dedicated folder with detailed README
- Use table of contents in each file for quick navigation
- Examples progress from simple to complex
- Key concepts are highlighted throughout
- All configurations tested in Cisco Packet Tracer

---

## 🛠️ Tools & Technologies

<div align="center">

| Tool | Purpose |
|------|---------|
| ![Cisco Packet Tracer](https://img.shields.io/badge/Cisco-Packet_Tracer-1BA0D7?style=flat-square&logo=cisco) | Network Simulation & Lab Implementation |
| ![Markdown](https://img.shields.io/badge/Markdown-Documentation-000000?style=flat-square&logo=markdown) | Documentation |
| ![Git](https://img.shields.io/badge/Git-Version_Control-F05032?style=flat-square&logo=git) | Version Control |
| ![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github) | Code Hosting & Collaboration |

</div>

---

## 📚 Prerequisites

Basic understanding of:
- Computer operations
- Network connectivity concepts
- Binary number system (helpful but not required)

---

## 📈 Progress Tracking

- **Topics Completed**: 22/22 ✅
- **Lab Exercises**: Comprehensive hands-on practice for each topic
- **Documentation**: Individual README for each topic
- **Projects**: Available on LinkedIn

---

## 🤝 Contributing

Feel free to:
- Report errors or unclear explanations
- Suggest additional examples
- Propose new topics for coverage

---

## 🤝 Connect With Me

<div align="center">

[![Email](https://img.shields.io/badge/Email-a.wahid7860668%40gmail.com-red?style=for-the-badge&logo=gmail)](mailto:a.wahid7860668@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Abdul_Wahid-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/abdul-wahid022)
[![GitHub](https://img.shields.io/badge/GitHub-abdul--wahid022-black?style=for-the-badge&logo=github)](https://github.com/abdul-wahid022)

</div>

---

## 📝 License

This repository is for educational purposes. Feel free to use the configurations and documentation for learning.

---

<div align="center">

**⭐ If you find this repository helpful, please consider giving it a star!**

*Last Updated: January 2026*

</div>

---
