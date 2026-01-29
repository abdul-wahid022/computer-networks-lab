# 🏢 Project 1: Mini Branch Network

<div align="center">

![Mini Branch](https://img.shields.io/badge/Project-Mini_Branch-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)
![Complexity](https://img.shields.io/badge/Complexity-⭐⭐⭐-orange?style=for-the-badge)

**A Compact Enterprise Branch Office Network Design**

[🏠 Back to Main Portfolio](README.md)

</div>

---

## 📖 Table of Contents

* [Overview](#-overview)
* [Network Topology](#-network-topology)
* [Project Specifications](#-project-specifications)
* [Technologies Implemented](#-technologies-implemented)
* [Network Architecture](#-network-architecture)
* [Configuration Highlights](#-configuration-highlights)
* [Learning Outcomes](#-learning-outcomes)

---

## 🎯 Overview

The **Mini Branch Network** is a comprehensive enterprise branch office implementation featuring 5 departments and a centralized server room. This project demonstrates fundamental enterprise networking concepts including redundancy, routing protocols, and network address translation.

### Key Features:
✅ 5 Department VLANs
✅ Centralized Server Room
✅ HSRP for High Availability
✅ OSPF Dynamic Routing
✅ PAT for Internet Connectivity
✅ Class B IP Addressing Scheme

---

## 🗺 Network Topology

<div align="center">
<img src="images/mini-branch-topology.png" alt="Mini Branch Network Topology" width="700">
</div>

### Topology Overview:
The network consists of multiple departments (represented by colored boxes) connected through a core distribution layer, with a central server room providing essential services.

---

## 📋 Project Specifications

| Specification | Details |
|--------------|---------|
| **Type** | Branch Office Network |
| **Scale** | Small to Medium |
| **Departments** | 5 Departments |
| **Additional** | 1 Server Room |
| **IP Scheme** | Class B (172.16.0.0/16) |
| **Routing Protocol** | OSPF |
| **Redundancy** | HSRP |
| **NAT Type** | PAT (Port Address Translation) |

---

## 🛠 Technologies Implemented

### 1. Routing Protocol
**OSPF (Open Shortest Path First)**
* Dynamic routing protocol
* Automatic route discovery
* Fast convergence
* Scalable for enterprise networks

```cisco
router ospf 1
 network 172.16.0.0 0.0.255.255 area 0
 passive-interface [interface]
```

### 2. High Availability
**HSRP (Hot Standby Router Protocol)**
* Provides gateway redundancy
* Automatic failover
* Eliminates single point of failure
* Virtual IP for default gateway

```cisco
interface [interface]
 standby 1 ip 172.16.x.1
 standby 1 priority 110
 standby 1 preempt
```

### 3. Network Address Translation
**PAT (Port Address Translation)**
* Multiple internal IPs share one public IP
* Conserves public IP addresses
* Provides security through address hiding

```cisco
ip nat inside source list 1 interface [outside-interface] overload
access-list 1 permit 172.16.0.0 0.0.255.255
```

### 4. VLAN Segmentation
**Department Isolation**
* Logical network separation
* Improved security
* Broadcast domain control
* Better traffic management

```cisco
vlan 10
 name DEPARTMENT-1
vlan 20
 name DEPARTMENT-2
! ... and so on
```
---
## 📊 IP Addressing Scheme

| Department | VLAN | Network | Gateway | Range |
|------------|------|---------|---------|-------|
| HR | 10 | 172.16.10.0/24 | 172.16.10.1 | 172.16.10.10-254 |
| Finance | 20 | 172.16.20.0/24 | 172.16.20.1 | 172.16.20.10-254 |
| IT | 30 | 172.16.30.0/24 | 172.16.30.1 | 172.16.30.10-254 |
| Sales | 40 | 172.16.40.0/24 | 172.16.40.1 | 172.16.40.10-254 |
| Management | 50 | 172.16.50.0/24 | 172.16.50.1 | 172.16.50.10-254 |
| Servers | 99 | 172.16.99.0/24 | 172.16.99.1 | 172.16.99.10-254 |

---
## 🎓 Learning Outcomes

### Skills Gained:

✅ **Network Design:**
* Branch office architecture
* Hierarchical network design
* Department segmentation
* Scalability planning

✅ **Routing:**
* OSPF configuration and operation
* Dynamic route propagation
* Route summarization
* Area design

✅ **High Availability:**
* HSRP implementation
* Active/Standby gateway setup
* Failover testing
* Redundancy planning

✅ **Network Address Translation:**
* PAT configuration
* Inside/Outside interface designation
* Access list creation
* Overload configuration

✅ **VLAN Design:**
* VLAN creation and assignment
* Inter-VLAN routing
* Trunk configuration
* VLAN best practices

✅ **Switching:**
* Layer 2 switching
* EtherChannel (optional)
* Spanning Tree Protocol
* Port security basics

---

## 🔍 Key Concepts Explained

### Why HSRP?
**Problem:** Single router = Single point of failure
**Solution:** HSRP provides automatic failover
* Two routers, one virtual IP
* If active router fails, standby takes over
* Seamless for end users
* Increased network uptime

### Why OSPF?
**Problem:** Static routing doesn't scale
**Solution:** OSPF automatically discovers routes
* Dynamic route updates
* Fast convergence
* Load balancing
* Suitable for enterprise

### Why PAT?
**Problem:** Limited public IP addresses
**Solution:** PAT allows many devices to share one IP
* Cost-effective
* Preserves public IP space
* Adds security layer
* Standard for branch offices

---

## 📈 Project Scalability

This design can scale by:
* Adding more departments (VLANs)
* Increasing server capacity
* Adding redundant links
* Implementing QoS for voice/video
* Extending to multiple branches with VPN

---

## 🔧 Troubleshooting Guide

### Common Issues:

**Issue 1: No Internet Connectivity**
```cisco
! Check NAT configuration
show ip nat translations
show ip nat statistics

! Verify outside interface
show ip interface brief | include outside
```

**Issue 2: HSRP Not Working**
```cisco
! Check HSRP status
show standby brief

! Verify priority and preempt
show standby [interface]
```

**Issue 3: OSPF Neighbors Not Forming**
```cisco
! Check OSPF configuration
show ip ospf neighbor
show ip ospf interface

! Verify network statements
show run | section router ospf
```

---

## 📝 Best Practices Implemented

✅ Hierarchical network design
✅ Redundancy at core layer
✅ VLAN segmentation for security
✅ Dynamic routing for scalability
✅ NAT for security and IP conservation
✅ Proper IP addressing scheme
✅ Documentation and labeling

---

## 🎯 Project Complexity

**Difficulty Level:** ⭐⭐⭐ (Intermediate)

**Time to Complete:** 4-6 hours

**Prerequisites:**
* Basic networking knowledge
* Cisco IOS command line
* Understanding of IP addressing
* VLAN concepts

---

## 📚 Related Projects

* **Next Step:** [Project 2 - Smart School Automation](02-SCHOOL-AUTOMATION-README.md)
* **Advanced Version:** [Project 3 - Head Quarter Network](03-HQ-NETWORK-README.md)
---
---
## 📞 Connect With Me

<div align="center">

[![Email](https://img.shields.io/badge/Email-a.wahid7860668%40gmail.com-red?style=for-the-badge&logo=gmail)](mailto:a.wahid7860668@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Abdul_Wahid-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/abdul-wahid022)
[![GitHub](https://img.shields.io/badge/GitHub-abdul--wahid022-black?style=for-the-badge&logo=github)](https://github.com/abdul-wahid022)

**💬 Questions? Need Packet Tracer files? Feel free to reach out!**

</div>


<div align="center">

[🏠 Back to Main Portfolio](README.md) | [➡️ Next Project](02-SCHOOL-AUTOMATION-README.md)

**Made with ❤️ by Abdul Wahid**

</div>
