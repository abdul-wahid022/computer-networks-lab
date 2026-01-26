
# 🌐 Routing Protocols - Complete Implementation Guide

<div align="center">

![Routing Banner](images/routing-banner.png)

**Comprehensive Guide to Static and Dynamic Routing Protocols**

[![Packet Tracer](https://img.shields.io/badge/Packet_Tracer-Lab_Tested-blue?style=for-the-badge&logo=cisco)](.)
[![Protocols](https://img.shields.io/badge/Protocols-5_Covered-green?style=for-the-badge)](.)
[![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)](.)

[📖 Overview](#-overview) • [🔧 Static Routing](#-static-routing) • [📡 RIP](#-rip-routing-information-protocol) • [⚡ EIGRP](#-eigrp-enhanced-interior-gateway-routing-protocol) • [🔗 OSPF](#-ospf-open-shortest-path-first) • [🌍 BGP](#-bgp-border-gateway-protocol)

</div>

---

## 📖 Overview

**Routing Protocols** are the backbone of network communication. They determine how data travels from source to destination across networks.

### What You'll Learn:

| Protocol | Type | Best For | Key Feature |
|----------|------|----------|-------------|
| **Static Routing** | Manual | Small networks | Complete control |
| **RIP** | Distance Vector | Small/Legacy | Simple configuration |
| **EIGRP** | Hybrid | Medium/Large Cisco | Fast convergence |
| **OSPF** | Link State | Enterprise | Scalable, hierarchical |
| **BGP** | Path Vector | Internet/ISP | Policy-based routing |

---

## 📚 Table of Contents

- [🔧 Static Routing](#-static-routing)
- [📡 RIP (Routing Information Protocol)](#-rip-routing-information-protocol)
- [⚡ EIGRP (Enhanced Interior Gateway Routing Protocol)](#-eigrp-enhanced-interior-gateway-routing-protocol)
- [🔗 OSPF (Open Shortest Path First)](#-ospf-open-shortest-path-first)
- [🌍 BGP (Border Gateway Protocol)](#-bgp-border-gateway-protocol)
- [📊 Protocol Comparison](#-protocol-comparison)
- [📝 Quick Reference](#-quick-reference)

---

## 🔧 Static Routing

### Concept

<div align="center">

| Feature | Details |
|---------|---------|
| **Type** | Manual configuration |
| **Updates** | None (manual only) |
| **Overhead** | Zero |
| **Control** | Complete |
| **Scalability** | Poor (manual effort) |
| **Use Case** | Small networks, stub networks |

</div>

### 🔑 Key Points:

**Static Routing** means manually configuring routes on each router.

#### Advantages:
- ✅ No CPU overhead (no routing updates)
- ✅ No bandwidth usage
- ✅ Complete control over routing
- ✅ Secure (no route advertisements)
- ✅ Predictable path selection

#### Disadvantages:
- ❌ Manual configuration required
- ❌ No automatic failover
- ❌ Not scalable for large networks
- ❌ Administrator must update manually
- ❌ No adaptation to network changes

#### When to Use:
```
✓ Small networks (< 10 routers)
✓ Stub networks (single path)
✓ Default routes to ISP
✓ Backup routes
✓ Security-sensitive paths
```

---

### Lab Implementation - Static Routing

#### 📊 Network Topology:

<p align="center">
  <img src="images/Static Routing/static-routing-topology.png" alt="Static Routing Topology" width="700">
</p>

#### 🎯 Scenario:

> **Objective:** Create a multi-router network with static routes enabling communication between different subnets.
>
> **Requirements:**
> - Configure IP addresses on all interfaces
> - Create static routes on all routers
> - Verify connectivity between all networks

---

### Configuration - Router 0

<p align="center">
  <img src="images/Static Routing/static-router0-config.png" alt="Router 0 Configuration" width="700">
</p>

```cisco
! Router 0 Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R0

! Interface Configuration
Router(config)# interface gigabitEthernet 0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit

Router(config)# interface gigabitEthernet 0/1
Router(config-if)# ip address 10.0.0.1 255.255.255.252
Router(config-if)# no shutdown
Router(config-if)# exit

! Static Routes to other networks
Router(config)# ip route 192.168.2.0 255.255.255.0 10.0.0.2
Router(config)# ip route 192.168.3.0 255.255.255.0 10.0.0.2
Router(config)# exit

! Verification
Router# show ip route
Router# show ip interface brief
```

---

### Configuration - Router 1

<p align="center">
  <img src="images/Static Routing/static-router1-config.png" alt="Router 1 Configuration" width="700">
</p>

```cisco
! Router 1 Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R1

! Interface Configuration
Router(config)# interface gigabitEthernet 0/0
Router(config-if)# ip address 10.0.0.2 255.255.255.252
Router(config-if)# no shutdown
Router(config-if)# exit

Router(config)# interface gigabitEthernet 0/1
Router(config-if)# ip address 10.0.0.5 255.255.255.252
Router(config-if)# no shutdown
Router(config-if)# exit

Router(config)# interface gigabitEthernet 0/2
Router(config-if)# ip address 192.168.2.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit

! Static Routes
Router(config)# ip route 192.168.1.0 255.255.255.0 10.0.0.1
Router(config)# ip route 192.168.3.0 255.255.255.0 10.0.0.6
Router(config)# exit
```

---

### Configuration - Router 2

<p align="center">
  <img src="images/Static Routing/static-router2-config.png" alt="Router 2 Configuration" width="700">
</p>

```cisco
! Router 2 Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R2

! Interface Configuration
Router(config)# interface gigabitEthernet 0/0
Router(config-if)# ip address 10.0.0.6 255.255.255.252
Router(config-if)# no shutdown
Router(config-if)# exit

Router(config)# interface gigabitEthernet 0/1
Router(config-if)# ip address 192.168.3.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit

! Static Routes
Router(config)# ip route 192.168.1.0 255.255.255.0 10.0.0.5
Router(config)# ip route 192.168.2.0 255.255.255.0 10.0.0.5
Router(config)# exit
```

---

### Results - Static Routing

#### ✅ Verification Output:

<p align="center">
  <img src="images/Static Routing/static-routing-output.png" alt="Static Routing Output" width="500">
</p>

**Result:** ✅ All routes successfully configured and connectivity verified between all networks

---

## 📡 RIP (Routing Information Protocol)

### Concept

<div align="center">

| Feature | Details |
|---------|---------|
| **Type** | Distance Vector |
| **Metric** | Hop Count (max 15) |
| **Algorithm** | Bellman-Ford |
| **Updates** | Every 30 seconds |
| **AD** | 120 |
| **Versions** | RIPv1 (classful), RIPv2 (classless) |

</div>

### 🔑 Key Points:

**RIP (Routing Information Protocol)** is one of the oldest and simplest routing protocols.

#### How It Works:
- Only counts **hops** (number of routers)
- Does **NOT** consider bandwidth or speed
- Maximum **15 hops** (16 = unreachable)
- Sends **full routing table** every 30 seconds

#### Real-Life Example:
```
Think of it like asking "How many cities to cross?"

Route A: Karachi → Hyderabad → Multan → Lahore (3 hops, slow roads)
Route B: Karachi → Motorway → Lahore (2 hops, fast motorway)

RIP chooses Route B (fewer hops)
✓ Even though both routes work, RIP only sees hop count
```

#### RIPv1 vs RIPv2:

| Feature | RIPv1 | RIPv2 |
|---------|-------|-------|
| **Subnet Mask** | ❌ Not sent | ✅ Sent with updates |
| **VLSM Support** | ❌ No | ✅ Yes |
| **Authentication** | ❌ No | ✅ Yes (MD5) |
| **Multicast** | ❌ Broadcast | ✅ 224.0.0.9 |
| **Classless** | ❌ Classful only | ✅ Classless |

#### Pizza Delivery Analogy:

**RIPv1 (Classful):**
```
Address: "House 123, Karachi"
Problem: Karachi is huge! Where exactly?
Result: Delivery boy guesses wrong location
```

**RIPv2 (Classless):**
```
Address: "House 123, Street 5, Block A, Gulshan, Karachi + GPS"
Result: ✅ Exact location delivered correctly
```

#### Problems with RIP:
- ❌ Ignores bandwidth (chooses 100Mbps 2-hop over 10Gbps 3-hop)
- ❌ Wastes bandwidth (broadcasts every 30 seconds)
- ❌ Not scalable (max 15 hops)
- ❌ Slow convergence (network changes take time)

#### Where to Use:
```
✓ Small office networks
✓ Lab environments  
✓ Legacy system compatibility
✗ Modern large networks (use OSPF/EIGRP instead)
```

---

### Lab Implementation - RIP

#### 📊 Network Topology:

<p align="center">
  <img src="images/RIP/rip-topology.png" alt="RIP Topology" width="700">
</p>

---

### Configuration - RIP Routers

<p align="center">
  <img src="images/RIP/rip-config-rip-ips.png" alt="RIP Configuration" width="700">
</p>

<p align="center">
  <img src="images/RIP/rip-config-routers.png" alt="RIP Configuration" width="700">
</p>

```cisco
! RIP Configuration (All Routers)
Router> enable
Router# configure terminal

! Enable RIP version 2
Router(config)# router rip
Router(config-router)# version 2
Router(config-router)# no auto-summary

! Advertise networks (classful network addresses)
Router(config-router)# network 192.168.1.0
Router(config-router)# network 192.168.2.0
Router(config-router)# network 10.0.0.0
Router(config-router)# exit

! Verification
Router# show ip route
Router# show ip protocols
Router# show ip rip database
```

#### 📝 Key Configuration Notes:
```
1. Use "version 2" for classless support (VLSM)
2. "no auto-summary" prevents automatic summarization
3. Network command uses classful addresses
4. RIP automatically discovers neighbors
```

---

### Results - RIP

#### ✅ R2 to R0 Connectivity:

<p align="center">
  <img src="images/RIP/rip-r2-to-r0.png" alt="RIP R2 to R0" width="700">
</p>

**Result:** ✅ Successful communication via RIP learned routes

---

#### ✅ R2 to R1 Connectivity:

<p align="center">
  <img src="images/RIP/rip-r2-to-r1.png" alt="RIP R2 to R1" width="700">
</p>

**Result:** ✅ All routers learning routes via RIP

---

## ⚡ EIGRP (Enhanced Interior Gateway Routing Protocol)

### Concept

<div align="center">

| Feature | Details |
|---------|---------|
| **Type** | Hybrid (Distance Vector + Link State) |
| **Algorithm** | DUAL (Diffusing Update Algorithm) |
| **Metric** | Bandwidth, Delay, Load, Reliability |
| **Updates** | Triggered (only changes) |
| **AD** | 90 (internal), 170 (external) |
| **Vendor** | Cisco proprietary |

</div>

### 🔑 Key Points:

**EIGRP** is Cisco's advanced hybrid routing protocol that combines the best of distance vector and link state protocols.

#### Key Features:
- ✅ **Fast convergence** - Adapts quickly to changes
- ✅ **Bandwidth efficient** - Only sends updates when changes occur
- ✅ **Unequal load balancing** - Can use multiple paths
- ✅ **DUAL algorithm** - Loop-free routing
- ✅ **Scalable** - Works well in medium to large networks

#### Real-Life Example - Google Maps:
```
You're not just choosing shortest distance, you consider:
├─ Traffic conditions (Load)
├─ Road quality (Reliability)  
├─ Speed limits (Bandwidth)
└─ Travel time (Delay)

EIGRP does the same for network routes!
```

#### Practical Scenario:
```
Company has 3 branches: Karachi, Lahore, Islamabad

Route 1: Karachi → Lahore
- Bandwidth: 100 Mbps
- Delay: 20ms

Route 2: Karachi → Islamabad → Lahore
- Bandwidth: 1 Gbps
- Delay: 5ms

EIGRP chooses Route 2 because:
✓ Higher bandwidth (1 Gbps vs 100 Mbps)
✓ Lower delay (5ms vs 20ms)
```

#### DUAL Algorithm Magic:

**Successor vs Feasible Successor:**

| Role | Description | Example |
|------|-------------|---------|
| **Successor** | Best route (currently used) | Main road home (10 mins) |
| **Feasible Successor** | Backup route (ready to use) | Alternate road (15 mins) |

```
Real-Life Example:
Main Road: 10 mins (Successor) ← Currently using
Back Road: 15 mins (Feasible Successor) ← Ready as backup

If main road blocked:
→ Instant switch to back road! ⚡
No recalculation needed!
```

#### Update Efficiency:

| Protocol | Update Behavior |
|----------|-----------------|
| **RIP** | Every 30 seconds: "Hey, I'm still here!" (annoying) |
| **EIGRP** | Only when changed: "Guys, Route B is down!" (smart) |

#### AS (Autonomous System) Number:

```
AS Number = Unique identifier for EIGRP process (1-65535)

RULE: Same AS number = Routers communicate
      Different AS = Routers DON'T communicate

Think of it like a "group code" for your EIGRP routers!
```

#### Where to Use:
```
✓ Cisco-dominated environments (banks, telecom)
✓ Medium to large enterprises
✓ Multi-location companies
✓ Networks requiring fast convergence
```

---

### Lab Implementation - EIGRP

#### 📊 Network Topology:

<p align="center">
  <img src="images/EIGRP/eigrp-topology.png" alt="EIGRP Topology" width="600">
</p>

---

### Configuration - Router 6

<p align="center">
  <img src="images/EIGRP/eigrp-router6-config.png" alt="EIGRP Router 6" width="500">
</p>

```cisco
! Router 6 - EIGRP Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R6

! Enable EIGRP with AS number 100
Router(config)# router eigrp 100
Router(config-router)# network 192.168.1.0 0.0.0.255
Router(config-router)# network 10.0.0.0 0.0.0.3
Router(config-router)# no auto-summary
Router(config-router)# exit

! Verification
Router# show ip eigrp neighbors
Router# show ip route eigrp
```

---

### Configuration - Router 0

<p align="center">
  <img src="images/EIGRP/eigrp-router0-config.png" alt="EIGRP Router 0" width="500">
</p>

```cisco
! Router 0 - EIGRP Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R0

! Enable EIGRP with AS number 100
Router(config)# router eigrp 100
Router(config-router)# network 10.0.0.0 0.0.0.3
Router(config-router)# network 10.0.0.4 0.0.0.3
Router(config-router)# no auto-summary
Router(config-router)# exit
```

---

### Configuration - Router 7

<p align="center">
  <img src="images/EIGRP/eigrp-router7-config.png" alt="EIGRP Router 7" width="500">
</p>

```cisco
! Router 7 - EIGRP Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R7

! Enable EIGRP with AS number 100
Router(config)# router eigrp 100
Router(config-router)# network 192.168.2.0 0.0.0.255
Router(config-router)# network 10.0.0.4 0.0.0.3
Router(config-router)# no auto-summary
Router(config-router)# exit
```

---

### Configuration - Router 1

<p align="center">
  <img src="images/EIGRP/eigrp-router1-config.png" alt="EIGRP Router 1" width="500">
</p>

```cisco
! Router 1 - EIGRP Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R1

! Enable EIGRP with AS number 100
Router(config)# router eigrp 100
Router(config-router)# network 192.168.3.0 0.0.0.255
Router(config-router)# no auto-summary
Router(config-router)# exit
```

---

### Results - EIGRP

#### ❌ Before EIGRP Configuration:

<p align="center">
  <img src="images/EIGRP/eigrp-before.png" alt="Before EIGRP" width="550">
</p>

**Status:** ❌ No connectivity between networks

---

#### ✅ After EIGRP Configuration:

<p align="center">
  <img src="images/EIGRP/eigrp-after.png" alt="After EIGRP" width="450">
</p>

**Status:** ✅ Full connectivity achieved with EIGRP routing

---

## 🔗 OSPF (Open Shortest Path First)

### Concept

<div align="center">

| Feature | Details |
|---------|---------|
| **Type** | Link State Protocol |
| **Algorithm** | Dijkstra (SPF) |
| **Metric** | Cost (bandwidth-based) |
| **AD** | 110 |
| **Standard** | Open Standard (RFC 2328) |
| **Scalability** | Excellent (hierarchical design) |

</div>

### 🔑 Key Points:

**OSPF** is like a smart GPS system for routers - complete network map with best path calculation.

#### Real-World Example - Google Maps:

| Google Maps | OSPF |
|-------------|------|
| Shows complete map | Complete network topology known |
| Calculates best route | Calculates shortest path |
| Avoids traffic | Chooses fast routes |
| Updates in real-time | Fast convergence |

#### Key Characteristics:
- ✅ **Complete topology knowledge** - Every router knows entire network
- ✅ **Fast convergence** - Changes propagate quickly
- ✅ **Scalable** - Handles large networks via areas
- ✅ **Loop-free** - Link state nature prevents loops
- ✅ **VLSM/CIDR support** - Classless routing
- ✅ **Hierarchical design** - Organized through areas

---

### OSPF Areas

#### Why Use Areas?

**Problem without areas:**
```
Single Area with 10,000 routers:
One cable disconnect →
├─ All 10,000 routers recalculate! 🔥
├─ CPU usage 100% on all routers
├─ Network hangs/becomes slow
└─ Entire network affected
```

**Solution with Multi-Area:**
```
Area 0 (Backbone): 500 routers
├─ Area 1 (Science): 2,000 routers
├─ Area 2 (Arts): 2,000 routers  
└─ Area 3 (Hostels): 2,000 routers

One cable in Area 1 disconnect →
├─ Only Area 1 recalculates ✓
├─ Areas 0, 2, 3 unaffected
├─ CPU usage limited to Area 1
└─ Fast convergence
```

#### Area Types:

| Area Type | External Routes | Type 5 LSA | Type 7 LSA | Default Route |
|-----------|-----------------|------------|------------|---------------|
| **Area 0 (Backbone)** | Yes | Yes | No | Optional |
| **Regular Area** | Yes | Yes | No | Optional |
| **Stub Area** | No | No | No | Mandatory |
| **Totally Stub** | No | No | No | Only route |
| **NSSA** | Limited | No | Yes | Optional |

#### Area 0 Rules:
```
⚠️ CRITICAL: Area 0 is MANDATORY
✓ All areas must connect to Area 0
✓ Cannot be fragmented
✓ Acts as backbone/hub
```

**Right Design (Hub & Spoke):**
```
       Area 1
          ↓
Area 2 → Area 0 ← Area 4
          ↑
       Area 3
```

**Wrong Design:**
```
❌ Area 1 → Area 2 → Area 0 (Area 1 not directly connected)
❌ Area 1 → Area 2 → Area 3 (No Area 0 at all)
```

---

### OSPF Router Types

#### 1. Internal Router
```
All interfaces in same area
├─ Single LSDB
└─ Neighbors only in same area
```

#### 2. ABR (Area Border Router)
```
Connects multiple areas
├─ Must have interface in Area 0
├─ Generates Type 3 LSA (Summary)
├─ Multiple LSDBs (one per area)
└─ Summarizes routes between areas
```

#### 3. ASBR (Autonomous System Boundary Router)
```
Connects OSPF to external protocols
├─ Generates Type 5 LSA (External)
├─ Performs redistribution
└─ Sources: Internet, RIP, EIGRP, BGP, Static
```

#### 4. Backbone Router
```
At least one interface in Area 0
└─ Routes within backbone area
```

---

### DR & BDR (Designated Router)

#### Problem Without DR/BDR:
```
10 Routers = 10 × 9 / 2 = 45 adjacencies!
→ Too many LSA exchanges
→ Bandwidth waste  
→ CPU overload
→ CHAOS! 🔥
```

#### Solution with DR/BDR:
```
Multi-Access Network (Switch/Ethernet):

R1  R2  R3  R4  R5
 │   │   │   │   │
 └───┴───┴───┴───┘
      [Switch]
         │
    DR elected
  (BDR as backup)
```

#### Roles:
- **DR** (Designated Router) - Leader, forms adjacency with all routers
- **BDR** (Backup DR) - Backup, takes over if DR fails
- **DROther** - Normal routers, only talk to DR/BDR

#### Election Criteria:
```
1. Highest OSPF Priority (default = 1, range 0-255)
2. If tie → Highest Router ID
3. Priority 0 = Never become DR/BDR
```

#### Benefit:
```
10 routers → Only 9 adjacencies (everyone to DR)
Instead of 45 adjacencies! ✓
```

---

### LSA (Link State Advertisement) Types

**LSA = Messages routers send to share network information**

#### Quick Reference:

| Type | Name | Generator | Scope | Purpose |
|------|------|-----------|-------|---------|
| **1** | Router LSA | Every router | Area | "I am this router with these links" |
| **2** | Network LSA | DR only | Area | "These routers on this network" |
| **3** | Summary LSA | ABR | Cross-area | "Other area has these networks" |
| **4** | ASBR Summary | ABR | Cross-area | "ASBR location is here" |
| **5** | External LSA | ASBR | Domain* | "External routes available" |
| **7** | NSSA External | ASBR (NSSA) | NSSA | "External in NSSA" |

*Except Stub/Totally Stub areas

#### Real-Life Analogies:

**Type 1:** "My name is Ali, my friends are Ahmed and Hassan, I live in Lahore"

**Type 2:** "Class monitor announces attendance: Ali, Ahmed, Hassan present"

**Type 3:** "Punjab office has 50 branches" (summarized, not exact addresses)

**Type 4:** "To reach the airport, use GT Road" (path to destination)

**Type 5:** "Internet sites available: google.com, facebook.com"

**Type 7:** "Local language message (Type 7) → Translation point converts to English (Type 5)"

---

### Lab Implementation - OSPF Single Area
OSPF/
#### 📊 Network Topology:

<p align="center">
  <img src="images/OSPF/ospf-single-area-topology.png" alt="OSPF Single Area" width="600">
</p>

---

### Configuration - Router 6 (OSPF)

<p align="center">
  <img src="images/OSPF/ospf-router6-config.png" alt="OSPF Router 6" width="500">
</p>

```cisco
! Router 6 - OSPF Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R6

! Enable OSPF Process 1
Router(config)# router ospf 1
Router(config-router)# network 192.168.1.0 0.0.0.255 area 0
Router(config-router)# network 10.0.0.0 0.0.0.3 area 0
Router(config-router)# router-id 6.6.6.6
Router(config-router)# exit

! Verification
Router# show ip ospf neighbor
Router# show ip ospf database
Router# show ip route ospf
```

---

### Configuration - Router 7 (OSPF)

<p align="center">
  <img src="images/OSPF/ospf-router7-config.png" alt="OSPF Router 7" width="500">
</p>

```cisco
! Router 7 - OSPF Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R7

! Enable OSPF Process 1
Router(config)# router ospf 1
Router(config-router)# network 192.168.2.0 0.0.0.255 area 0
Router(config-router)# network 10.0.0.4 0.0.0.3 area 0
Router(config-router)# router-id 7.7.7.7
Router(config-router)# exit
```

---

### Configuration - Router 0 (OSPF)

<p align="center">
  <img src="images/OSPF/ospf-router0-config.png" alt="OSPF Router 0" width="500">
</p>

```cisco
! Router 0 - OSPF Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R0

! Enable OSPF Process 1
Router(config)# router ospf 1
Router(config-router)# network 10.0.0.0 0.0.0.3 area 0
Router(config-router)# network 10.0.0.4 0.0.0.3 area 0
Router(config-router)# router-id 1.1.1.1
Router(config-router)# exit
```

---
### Lab Implementation - OSPF Single-Area Result
<p align="center">
  <img src="images/OSPF/ospf-output.png" alt="OSPF Router 0" width="500">
</p>

### Lab Implementation - OSPF Multi-Area

#### 📊 Network Topology:

<p align="center">
  <img src="images/OSPF/ospf-multi-area-topology.png" alt="OSPF Multi-Area" width="600">
</p>

---

### Configuration - R-A2 (Area 2)

<p align="center">
  <img src="images/OSPF/ospf-ra2-config.png" alt="R-A2 Configuration" width="500">
</p>

```cisco
! R-A2 - OSPF Multi-Area Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R-A2

! OSPF Configuration
Router(config)# router ospf 
Router(config-router)# network 192.168.2.0 0.0.0.255 area 2
Router(config-router)# network 10.0.0.8 0.0.0.3 area 2
Router(config-router)# router-id 2.2.2.2
Router(config-router)# exit
```

---

### Configuration - R-A0 (Backbone Area 0)

<p align="center">
  <img src="images/OSPF/ospf-ra0-config.png" alt="R-A0 Configuration" width="500">
</p>

```cisco
! R-A0 - Backbone Router Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R-A0

! OSPF Configuration (ABR - connects areas)
Router(config)# router ospf 1
Router(config-router)# network 10.0.0.0 0.0.0.3 area 0
Router(config-router)# network 10.0.0.4 0.0.0.3 area 0
Router(config-router)# network 10.0.0.8 0.0.0.3 area 2
Router(config-router)# router-id 10.10.10.10
Router(config-router)# exit
```

---

### Configuration - R-A1 (Area 1)

<p align="center">
  <img src="images/OSPF/ospf-ra1-config.png" alt="R-A1 Configuration" width="500">
</p>

```cisco
! R-A1 - OSPF Multi-Area Configuration
Router> enable
Router# configure terminal
Router(config)# hostname R-A1

! OSPF Configuration
Router(config)# router ospf 1
Router(config-router)# network 192.168.1.0 0.0.0.255 area 1
Router(config-router)# network 10.0.0.0 0.0.0.3 area 1
Router(config-router)# router-id 1.1.1.1
Router(config-router)# exit
```

---

### Configuration - Main Router (ABR)

<p align="center">
  <img src="images/OSPF/ospf-main-router-config.png" alt="Main Router Configuration" width="500">
</p>

```cisco
! Main Router - ABR Configuration
Router> enable
Router# configure terminal
Router(config)# hostname Main-Router

! OSPF Configuration (connects Area 0 and Area 1)
Router(config)# router ospf 1
Router(config-router)# network 10.0.0.0 0.0.0.3 area 1
Router(config-router)# network 10.0.0.4 0.0.0.3 area 0
Router(config-router)# router-id 100.100.100.100
Router(config-router)# exit
```

---

### Results - OSPF

#### ✅ OSPF Verification:

<p align="center">
  <img src="images/OSPF/ospf-verification.png" alt="OSPF Verification" width="550">
</p>

**Commands Used:**
```cisco
show ip ospf neighbor
show ip ospf database  
show ip route ospf
show ip protocols
```

---

#### ✅ Successful Connectivity:

<p align="center">
  <img src="images/OSPF/ospf-successful-ping.png" alt="Successful Ping" width="550">
</p>

**Result:** ✅ Full connectivity between all areas via OSPF

---

## 🌍 BGP (Border Gateway Protocol)

### Concept

<div align="center">

| Feature | Details |
|---------|---------|
| **Type** | Path Vector Protocol |
| **Port** | TCP 179 |
| **Metric** | Path Attributes (policy-based) |
| **AD** | eBGP = 20, iBGP = 200 |
| **Standard** | Open Standard (RFC 4271) |
| **Scope** | Internet backbone |

</div>

### 🔑 Key Points:

**BGP** is the Internet's GPS system - routing between companies (ISPs).

#### Real-World Example - International Courier:

```
Sending parcel Pakistan → America:

Pakistan Post → Dubai Hub → London Hub → New York → Delivery
    AS 1    →    AS 2   →    AS 3    →   AS 4   → Customer

Each hub (AS) has its own policy:
├─ Dubai: "Only premium parcels accepted"
├─ London: "Prefer traffic from Asia"
└─ New York: "Choose shortest path"
```

---

### AS (Autonomous System)

**Simple:** One company's complete network  
**Technical:** Group of IP networks under single administrative control

#### Real Examples:
```
AS 100 = PTCL (Pakistan Telecom)
AS 200 = Nayatel (Pakistan ISP)
AS 300 = Level3 (International ISP)
AS 400 = Google
AS 500 = Facebook
AS 600 = Amazon
```

#### AS Types:

**1. Stub AS:**
```
    Internet
       ↓
    [AS 100]
       ↓
   Single ISP

- Connected to one ISP only
- No transit traffic
- Example: Small company with one internet connection
```

**2. Multi-homed AS:**
```
      Internet
      ↙     ↘
   ISP-1   ISP-2
      ↘     ↙
      [AS 200]

- Multiple ISP connections
- Redundancy
- No transit traffic
- Example: Large company with backup links
```

**3. Transit AS:**
```
AS-A → [AS 300] → AS-B
       (Transit)

- Forwards others' traffic
- ISP business model
- Example: Level3, Telia, NTT
```

#### AS Number Ranges:
```
Public AS:  1 - 64,511 (Used on Internet)
Private AS: 64,512 - 65,535 (Internal testing)
```

---

### eBGP vs iBGP

#### Visual Comparison:

```
Company A (AS 100)          Company B (AS 200)
┌─────────────────────┐    ┌─────────────────────┐
│ R1 ←─iBGP─→ R2     │    │ R3 ←─iBGP─→ R4     │
│  ↓          ↓       │    │  ↓          ↓       │
│ R5 ←─iBGP─→ R6     │    │ R7 ←─iBGP─→ R8     │
└──────────┬──────────┘    └──────────┬──────────┘
           │                          │
           └────────eBGP──────────────┘
        (Different AS = External)
```

#### eBGP (External BGP):

| Feature | Details |
|---------|---------|
| **Purpose** | Between different companies |
| **Next-hop** | Changes |
| **AS-Path** | AS number added |
| **TTL** | Default 1 (directly connected) |
| **AD** | 20 |

**Example:** PTCL (AS 100) → Level3 (AS 300)

#### iBGP (Internal BGP):

| Feature | Details |
|---------|---------|
| **Purpose** | Same company, different locations |
| **Next-hop** | Preserved |
| **AS-Path** | Unchanged |
| **TTL** | Default 255 |
| **AD** | 200 |
| **Requirement** | Full mesh or Route Reflectors |

**Example:** PTCL Karachi ↔ PTCL Lahore (Same AS 100)

---

### BGP Path Selection

#### Attribute Priority (HIGH to LOW):

```
1. Weight (Highest) ← Cisco only, local to router
2. Local Preference ← Local to AS
3. Locally Originated ← Self-originated routes
4. AS Path (Shortest) ← Number of AS hops
5. Origin Type ← IGP > EGP > Incomplete
6. MED (Lowest) ← Multi-Exit Discriminator
7. eBGP > iBGP ← Prefer external
8. IGP Metric ← Internal cost
9. Oldest eBGP ← Stability
10. Lowest Router ID ← Tiebreaker
```

#### Key Attributes Explained:

**1. Weight (Cisco Only):**
```
Your personal preference for routes
Range: 0-65,535 (higher = better)

Example:
Pizza Hut = Weight 100 ← You prefer this
Dominos = Weight 50
Result: You always choose Pizza Hut!
```

**2. Local Preference:**
```
Company-wide preference
Range: 0-4,294,967,295 (higher = better)
Default: 100

Example:
Company has 2 internet links:
Link A (Fiber) = Local Pref 200 ← Everyone uses this
Link B (DSL) = Local Pref 100
Boss says: "Everyone use Link A!"
```

**4. AS Path Length:**
```
Rule: Shortest path wins

Route 1: PTCL → Google
AS Path: 100, 400 (Length = 2) ✓ Better!

Route 2: PTCL → Level3 → Telia → Google  
AS Path: 100, 300, 500, 400 (Length = 4)

Decision: Route 1 (fewer hops = less latency)
```

**6. MED (Multi-Exit Discriminator):**
```
Suggestion to neighbor (lower = better)
Range: 0-4,294,967,295

Example: Shopping Mall with 2 gates
Gate 1: MED = 50 (less traffic) ← Suggested
Gate 2: MED = 100 (more traffic)
Mall says: "Please use Gate 1!"
```

---

### BGP States

#### State Progression (Like Tinder Match):

```
1. Idle        → "App opened, no search yet"
2. Connect     → "Match request sent"
3. Active      → "Waiting for response"
4. OpenSent    → "Hi! message sent"
5. OpenConfirm → "Hello! reply received"
6. Established → "Normal chat working!" ✓
```

#### Detailed States:

| State | Description | Real-Life |
|-------|-------------|-----------|
| **Idle** | BGP initialized, no connection | App installed, making profile |
| **Connect** | TCP connection attempt | Match request sent |
| **Active** | Connection failed, retrying | Connection not working, trying again |
| **OpenSent** | TCP established, Open message sent | Connection made, "Hi!" sent |
| **OpenConfirm** | Open received, waiting for Keepalive | "Hello!" reply received |
| **Established** | Fully operational! Routes exchanging | Normal conversation flowing ✓ |

---

### BGP Message Types

#### 1. Open Message:
```
Purpose: Establish neighbor relationship
Contains:
- BGP Version (4)
- AS Number
- Hold Time
- Router ID
```

#### 2. Update Message:
```
Purpose: Advertise/withdraw routes
Contains:
- Withdrawn Routes
- Path Attributes
- NLRI (Network Layer Reachability Info)
```

#### 3. Keepalive Message:
```
Purpose: Keep connection alive
Frequency: Every 60 seconds (default)
```

#### 4. Notification Message:
```
Purpose: Report errors and close connection
Contains:
- Error code
- Error subcode
Result: Connection terminates
```

---

### BGP Use Cases

#### 1. Internet Service Providers (ISPs):
```
PTCL (AS 100) connects to:
├─ International ISPs (Level3, Telia)
├─ Local ISPs (Nayatel, StormFiber)
├─ Content providers (Google, Facebook)
└─ Peering exchanges (PKIX)
```

#### 2. Large Enterprises:
```
Large Bank:
├─ Multiple ISP connections (redundancy)
├─ Multiple branch locations
├─ Need traffic path control
└─ Load balancing & failover
```

#### 3. Content Delivery Networks:
```
Google (AS 15169):
├─ Presence in 100+ countries
├─ Direct peering with ISPs
├─ Multiple data centers
└─ Anycast addressing
```

---
BGP/
### Lab Implementation - BGP

#### 📊 Network Topology:

<p align="center">
  <img src="images/BGP/bgp-topology.png" alt="BGP Topology" width="600">
</p>

---

### Configuration - R-L (Left Router)

<p align="center">
  <img src="images/BGP/bgp-rl-config.png" alt="BGP R-L Configuration" width="500">
</p>

```cisco
! R-L - BGP Configuration (AS 100)
Router> enable
Router# configure terminal
Router(config)# hostname R-L

! BGP Configuration
Router(config)# router bgp 100
Router(config-router)# neighbor 10.0.0.2 remote-as 200
Router(config-router)# network 192.168.1.0 mask 255.255.255.0
Router(config-router)# exit

! Verification
Router# show ip bgp summary
Router# show ip bgp neighbors
```

---

### Configuration - R-R (Right Router)

<p align="center">
  <img src="images/BGP/bgp-rr-config.png" alt="BGP R-R Configuration" width="500">
</p>

```cisco
! R-R - BGP Configuration (AS 300)
Router> enable
Router# configure terminal
Router(config)# hostname R-R

! BGP Configuration
Router(config)# router bgp 300
Router(config-router)# neighbor 10.0.0.6 remote-as 200
Router(config-router)# network 192.168.3.0 mask 255.255.255.0
Router(config-router)# exit
```

---

### Configuration - R-M (Middle Router)

<p align="center">
  <img src="images/BGP/bgp-rm-config.png" alt="BGP R-M Configuration" width="500">
</p>

```cisco
! R-M - BGP Configuration (AS 200 - Transit)
Router> enable
Router# configure terminal
Router(config)# hostname R-M

! BGP Configuration (eBGP with both neighbors)
Router(config)# router bgp 200
Router(config-router)# neighbor 10.0.0.1 remote-as 100
Router(config-router)# neighbor 10.0.0.5 remote-as 300
Router(config-router)# network 192.168.2.0 mask 255.255.255.0
Router(config-router)# exit
```

---

### Results - BGP

#### ✅ BGP Verification:

<p align="center">
  <img src="images/BGP/bgp-verification.png" alt="BGP Verification" width="450">
</p>

**Commands Used:**
```cisco
show ip bgp summary
show ip bgp neighbors
show ip bgp
show ip route bgp
```

---

#### ✅ BGP Output:

<p align="center">
  <img src="images/BGP/bgp-output.png" alt="BGP Output" width="700">
</p>

**Result:** ✅ BGP neighbors established, routes exchanged successfully

---

## 📊 Protocol Comparison

### Routing Protocols Side-by-Side

<div align="center">

| Feature | Static | RIP | EIGRP | OSPF | BGP |
|---------|--------|-----|-------|------|-----|
| **Type** | Manual | Distance Vector | Hybrid | Link State | Path Vector |
| **Metric** | N/A | Hop Count | Composite | Cost | Path Attributes |
| **AD** | 1 | 120 | 90 | 110 | eBGP: 20, iBGP: 200 |
| **Updates** | None | Every 30s | Triggered | Triggered | Triggered |
| **Convergence** | N/A | Slow | Fast | Fast | Slow |
| **Scalability** | Poor | Small | Medium-Large | Large | Internet-scale |
| **CPU Usage** | None | Low | Moderate | High | High |
| **Memory** | Low | Low | Moderate | High | Very High |
| **Max Hop** | N/A | 15 | 255 | N/A | N/A |
| **VLSM** | Yes | RIPv2: Yes | Yes | Yes | Yes |
| **Loop Prevention** | Admin | Split Horizon | DUAL | SPF | AS Path |
| **Best For** | Stub networks | Small/Legacy | Cisco networks | Enterprise | Internet/ISP |

</div>

---

### When to Use Which Protocol?

```
📌 Static Routing:
✓ Small networks (< 10 routers)
✓ Stub networks (single exit point)
✓ Default routes to ISP
✓ Maximum security needed

📌 RIP:
✓ Small office networks
✓ Legacy system compatibility
✓ Simple configuration needed
✗ Avoid for modern networks

📌 EIGRP:
✓ Cisco-only environments
✓ Medium to large networks
✓ Fast convergence needed
✓ Unequal load balancing required

📌 OSPF:
✓ Large enterprise networks
✓ Multi-vendor environment
✓ Hierarchical design needed
✓ Open standard required

📌 BGP:
✓ ISP networks
✓ Internet routing
✓ Multi-homing (multiple ISPs)
✓ Policy-based routing needed
```

---

## 📝 Quick Reference

### Common Commands by Protocol

#### Static Routing:
```cisco
ip route [destination] [mask] [next-hop|interface]
ip route 0.0.0.0 0.0.0.0 [next-hop]  # Default route
show ip route static
```

#### RIP:
```cisco
router rip
 version 2
 no auto-summary
 network [network-address]

show ip route rip
show ip protocols
```

#### EIGRP:
```cisco
router eigrp [AS-number]
 network [network] [wildcard-mask]
 no auto-summary

show ip eigrp neighbors
show ip eigrp topology
show ip route eigrp
```

#### OSPF:
```cisco
router ospf [process-id]
 network [network] [wildcard-mask] area [area-id]
 router-id [router-id]

show ip ospf neighbor
show ip ospf database
show ip route ospf
```

#### BGP:
```cisco
router bgp [AS-number]
 neighbor [IP] remote-as [AS-number]
 network [network] mask [mask]

show ip bgp summary
show ip bgp neighbors
show ip bgp
```

---

### Verification Commands

```cisco
# Universal Commands (all protocols)
show ip route
show ip interface brief
show running-config
ping [destination]
traceroute [destination]

# Protocol Specific
show ip protocols               # Shows all routing protocols
show ip route [protocol]        # Shows routes for specific protocol

# Debugging (use carefully)
debug ip routing
debug ip [protocol]
```

---



---

## 🎓 What I Learned

### Static Routing:
✅ Manual route configuration and management  
✅ Complete control over routing decisions  
✅ Use cases for stub networks and security  
✅ Default route configuration  

### RIP:
✅ Distance vector protocol fundamentals  
✅ Hop count metric limitations  
✅ Difference between RIPv1 and RIPv2  
✅ When NOT to use RIP in modern networks  

### EIGRP:
✅ Hybrid protocol combining best of both worlds  
✅ DUAL algorithm for loop-free routing  
✅ Composite metric calculation  
✅ Successor and Feasible Successor concepts  
✅ Fast convergence mechanisms  

### OSPF:
✅ Link state protocol operation  
✅ Hierarchical design with areas  
✅ Area types and their purposes  
✅ LSA types and their functions  
✅ DR/BDR election process  
✅ Multi-area design and benefits  

### BGP:
✅ Internet routing fundamentals  
✅ Autonomous System concepts  
✅ eBGP vs iBGP differences  
✅ Path selection attributes  
✅ BGP states and neighbor relationships  
✅ Policy-based routing decisions  

---

## 🚀 How to Use This Repository

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/Routing-Protocols.git
   ```

2. **Study each protocol:**
   - Start with concepts
   - Understand topology diagrams
   - Follow configuration steps
   - Analyze output results

3. **Practice in lab:**
   - Replicate topologies in Packet Tracer
   - Apply configurations
   - Test connectivity
   - Troubleshoot issues

4. **Compare protocols:**
   - Understand use cases
   - Know when to use which protocol
   - Practice protocol selection decisions

---

## 📞 Connect With Me

<div align="center">

[![Email](https://img.shields.io/badge/Email-a.wahid7860668%40gmail.com-red?style=for-the-badge&logo=gmail)](mailto:a.wahid7860668@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Abdul_Wahid-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/abdul-wahid022)
[![GitHub](https://img.shields.io/badge/GitHub-abdul--wahid022-black?style=for-the-badge&logo=github)](https://github.com/abdul-wahid022)

**💬 Questions? Need Packet Tracer files? Feel free to reach out!**

</div>

---

## 📄 License

This project is created for **educational purposes** and is open-source.

---

<div align="center">

### ⭐ If you found this helpful, please give it a star!

**Made with 💙 by ABDUL WAHID**

*Last Updated: January 2026*

</div>
