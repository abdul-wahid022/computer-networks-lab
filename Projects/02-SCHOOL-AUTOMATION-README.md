# 🏫 Project 2: Smart School Automation System

<div align="center">

![School Automation](https://img.shields.io/badge/Project-Smart_School-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)
![IoT](https://img.shields.io/badge/IoT-Enabled-orange?style=for-the-badge)

**An Innovative MCU-Controlled School Automation Network**

[🏠 Back to Main Portfolio](README.md)

</div>

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Network Topology](#-network-topology)
- [Project Specifications](#-project-specifications)
- [MCU & IoT Integration](#-mcu--iot-integration)
- [Network Sections](#-network-sections)
- [Automation Features](#-automation-features)
- [Configuration](#-configuration)
- [Learning Outcomes](#-learning-outcomes)

---

## 🎯 Overview

The **Smart School Automation System** is an innovative project that combines traditional networking with IoT and automation technologies. This project demonstrates how a **Microcontroller Unit (MCU)** can be programmed with Java to control various school devices, creating a smart and automated learning environment.

### Key Innovation:
✅ MCU-based automation (Java programming)
✅ Timer-controlled bell/siren system
✅ Automated fan and AC control
✅ Motion detector entrance security
✅ Smart classroom management
✅ Emergency response integration
✅ Environmental monitoring

---

## 🗺 Network Topology

<div align="center">
<img src="images/mini-school-automation-topology.png" alt="Smart School Topology" width="700">
</div>

### Topology Sections:
- **Top Left:** Emergency System
- **Top Right/Center:** Access Host & Core Network
- **Right:** Admin Section with Servers
- **Bottom (Blue Box):** Smart Classroom (Main Innovation)
- **Left Side:** Various smart sensors and IoT devices

---

## 📋 Project Specifications

| Specification | Details |
|--------------|---------|
| **Type** | Smart School IoT Network |
| **Scale** | Single Campus |
| **Main Technology** | MCU (Microcontroller) |
| **Programming** | Java for MCU |
| **Key Feature** | Automated Bell & Device Control |
| **IoT Devices** | Fans, AC, Lights, Sensors |
| **Security** | Motion Detectors, Access Control |

---

## 🤖 MCU & IoT Integration

### What is MCU?

**MCU = Microcontroller Unit**

A small computer on a single integrated circuit that can be programmed to control various devices and sensors.

### How It Works in This Project:

```
┌─────────────────────────────────────────────┐
│           MCU CONTROL CENTER                │
│     (Programmed with Java Code)             │
└──────────────┬──────────────────────────────┘
               │
       ┌───────┼───────┬───────┬────────┐
       │               │       │        │
   ┌───▼───┐      ┌───▼───┐ ┌─▼──┐  ┌──▼───┐
   │ Timer │      │  Fan  │ │ AC │  │Lights│
   │ Bell  │      │Control│ │Ctrl│  │ Ctrl │
   └───────┘      └───────┘ └────┘  └──────┘
```
---

## 🏗 Network Sections

### 1. 🚨 Emergency System (Top Left)

**Components:**
- Emergency Access Point (E-PAN)
- Smart Home/IoT Ethernet devices
- Appliance Entrance sensors
- E-FIRE alarm system
- Siren Enterprise device

**Purpose:**
- Emergency communication
- Fire detection and alarm
- Quick response system
- Safety monitoring

**Connectivity:**
- Connected to Access Host
- Wireless emergency access
- Wired backup connections

---

### 2. 🖥 Admin Section (Right Side - Black Box)

**Components:**
- Admin Server Room
- PC-PT (Admin PC)
- Server-PT (Selection Server)

**Functions:**
- Central management
- User authentication
- Data storage
- System monitoring
- Configuration management

**Network Details:**
- Dedicated server VLAN
- Secure access controls
- High-speed connectivity to core

---

### 3. 📚 Smart Classroom (Bottom - Blue Box Highlighted)

**This is the MAIN INNOVATION of the project!**

**Components:**
- **CLASS-B2100:** Smart controller
- **Air Conditioner (CL-AC):** Climate control
- **4 Laptop-PT (Student):** Student laptops (Student#1-4)
- **CL Lamp#1 & CL Lamp#2:** Smart lights
- **Door (CL-Door):** Automated entry
- **Smoke Detector (CL-SR05):** Safety sensor
- **CO Detector (CL-CO#1):** Environmental monitoring
- **CL-Home#1 Monitor:** Status display
- **Water Level Monitor (CL-Humid):** Environmental control

**Smart Features:**

```
🔔 Automated Bell System
   ├─ Timer-based ringing
   ├─ Different tones for different times
   └─ Synchronized across campus

🌡️ Climate Control
   ├─ AC auto-adjust based on temperature
   ├─ Fan speed based on occupancy
   └─ Energy-efficient operation

💡 Lighting System
   ├─ Auto on/off based on time
   ├─ Motion-activated
   └─ Brightness adjustment

🚪 Access Control
   ├─ Automated door lock/unlock
   ├─ Time-based access
   └─ Emergency override

🔥 Safety Systems
   ├─ Smoke detection
   ├─ CO monitoring
   ├─ Water level alerts
   └─ Emergency notifications
```

---

### 4. 🌐 Core Network (Center)

**Main Devices:**
- **Access Host:** Central connectivity point
- **Core Switches:** Distribution layer
- **Wireless Controller:** Wi-Fi management
- **Motion Detectors:** Environmental sensing

**Connected To:**
- Emergency system
- Classroom
- Admin section
- IoT devices

---

### 5. 📡 IoT Devices Network (Left Side)

**Smart Devices:**
- Lawn Sprinkler (Siren Enterprise#2)
- Web Camera
- Webcam Car (Mobile monitoring)
- Door IoT sensors
- Environmental sensors

**Functions:**
- Campus monitoring
- Security surveillance
- Environmental control
- Remote management

---

## ⚙️ Automation Features

### 1. Timer-Based Bell System

**How It Works:**
```
MCU Timer → Check Schedule → Ring Bell → Control Devices
```

**Bell Schedule Example:**
| Time | Event | Device Actions |
|------|-------|----------------|
| 08:00 | School Start | Unlock doors, Turn on lights |
| 09:45 | Break Start | Ring bell, AC to economy mode |
| 10:00 | Classes Resume | Ring bell, AC normal mode |
| 12:30 | Lunch Break | Ring bell, Lights to minimum |
| 13:30 | Classes Resume | Ring bell, Full power mode |
| 15:30 | School End | Ring bell, Lock doors, Lights off |

---

### 2. Smart Fan Control

**Control Logic:**
```java
if (temperature > 28°C && occupancy > 10) {
    fanSpeed = HIGH;
} else if (temperature > 25°C) {
    fanSpeed = MEDIUM;
} else {
    fanSpeed = LOW;
}
```

**Features:**
- Temperature-based speed control
- Occupancy detection
- Energy-efficient operation
- Manual override option

---

### 3. Motion Detector System

**Locations:**
- Entrance gates
- Classroom doors
- Emergency exits
- Server room

**Functions:**
- Detect movement
- Trigger lights
- Log access
- Security alerts

---

### 4. Environmental Monitoring

**Sensors:**
- **Smoke Detector:** Fire safety
- **CO Detector:** Air quality
- **Water Level Monitor:** Flood prevention
- **Temperature Sensors:** Climate control
- **Humidity Sensors:** Comfort monitoring

**Alerts:**
```
IF smoke_detected:
    → Sound alarm
    → Send notification to admin
    → Activate sprinkler system
    → Unlock emergency exits
```

---

## 🔧 Configuration Examples

### MCU Setup (Java)

```java
// Main School Automation Class
public class SchoolAutomation {
    
    // Device objects
    Bell schoolBell;
    Fan[] classroomFans;
    AC[] airConditioners;
    Light[] lights;
    Door[] doors;
    
    // Sensors
    MotionSensor[] motionSensors;
    SmokeSensor[] smokeSensors;
    COSensor[] coSensors;
    
    // Timer for scheduled events
    ScheduledExecutorService scheduler;
    
    public void initialize() {
        // Initialize all devices
        setupDevices();
        setupSensors();
        startScheduler();
    }
    
    public void runBellSchedule() {
        scheduler.scheduleAtFixedRate(() -> {
            LocalTime now = LocalTime.now();
            checkBellTime(now);
        }, 0, 1, TimeUnit.SECONDS);
    }
    
    private void checkBellTime(LocalTime now) {
        for (BellTime bt : bellSchedule) {
            if (now.equals(bt.time)) {
                schoolBell.ring(bt.duration);
                performScheduledActions(bt.actions);
            }
        }
    }
    
    public void performScheduledActions(Actions actions) {
        if (actions.contains(LIGHTS_ON)) {
            turnOnAllLights();
        }
        if (actions.contains(DOORS_UNLOCK)) {
            unlockAllDoors();
        }
        // More actions...
    }
    
    // Emergency response
    public void handleEmergency(EmergencyType type) {
        switch(type) {
            case FIRE:
                soundAlarm();
                unlockEmergencyExits();
                notifyFireDepartment();
                break;
            case INTRUSION:
                lockDoors();
                alertSecurity();
                recordCCTV();
                break;
        }
    }
}
```
---

## 🎓 Learning Outcomes

### Technical Skills:

✅ **IoT Integration:**
- MCU programming with Java
- Sensor integration
- Device automation
- Real-time control systems

✅ **Network Design:**
- IoT device networking
- VLAN segmentation for IoT
- Wireless network for sensors
- Secure device communication

✅ **Automation:**
- Timer-based scheduling
- Event-driven programming
- Conditional logic for devices
- Emergency response systems

✅ **Smart Building:**
- Climate control automation
- Lighting management
- Access control systems
- Environmental monitoring

✅ **Programming:**
- Java for embedded systems
- Object-oriented design
- Event handling
- Scheduling algorithms

---

## 🔍 Key Innovations

### 1. MCU-Controlled Bell System
**Traditional:** Manual bell ringing
**Smart:** Automated, timer-based, consistent

### 2. Intelligent Climate Control
**Traditional:** Manual AC/fan switches
**Smart:** Auto-adjust based on temperature and occupancy

### 3. Automated Access Control
**Traditional:** Manual door locks
**Smart:** Time-based, scheduled lock/unlock

### 4. Integrated Safety
**Traditional:** Separate alarm systems
**Smart:** Connected, automated response

---

## 🚀 Future Enhancements

Possible upgrades:
- AI-based attendance system using cameras
- Energy consumption monitoring and optimization
- Mobile app for remote control
- Voice-activated classroom controls
- Integration with learning management systems
- Predictive maintenance for devices

---

## 📈 Project Benefits

**For Students:**
- Comfortable learning environment
- Modern technology exposure
- Safe and secure campus

**For Teachers:**
- Less time on manual tasks
- Better classroom control
- Focus on teaching

**For Administration:**
- Energy savings
- Centralized control
- Better resource management
- Safety improvements

**For Environment:**
- Reduced energy waste
- Efficient resource usage
- Smart power management

---

## 🔧 Troubleshooting

### Common Issues:

**Issue 1: Bell Not Ringing on Time**
```java
// Check timer configuration
System.out.println("Current Time: " + getCurrentTime());
System.out.println("Scheduled Times: " + bellSchedule);

// Verify MCU connection
checkMCUConnection();
```

**Issue 2: Sensors Not Responding**
```cisco
! Check VLAN connectivity
show vlan brief
show interfaces status

! Verify sensor power
show power inline
```

**Issue 3: AC Not Auto-Adjusting**
```java
// Debug temperature reading
System.out.println("Current Temp: " + temperatureSensor.read());
System.out.println("AC Mode: " + ac.getMode());

// Check control logic
verifyControlAlgorithm();
```

---

## 🎯 Project Complexity

**Difficulty Level:** ⭐⭐⭐ (Intermediate-Advanced)

**Time to Complete:** 6-8 hours

**Prerequisites:**
- Basic networking knowledge
- Java programming basics
- Understanding of IoT concepts
- Packet Tracer IoT components

---

## 📚 Related Projects

- **Previous:** [Project 1 - Mini Branch Network](01-MINI-BRANCH-README.md)
- **Next:** [Project 3 - Head Quarter Network](03-HQ-NETWORK-README.md)

---

## 📞 Connect With Me

<div align="center">

[![Email](https://img.shields.io/badge/Email-a.wahid7860668%40gmail.com-red?style=for-the-badge&logo=gmail)](mailto:a.wahid7860668@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Abdul_Wahid-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/abdul-wahid022)
[![GitHub](https://img.shields.io/badge/GitHub-abdul--wahid022-black?style=for-the-badge&logo=github)](https://github.com/abdul-wahid022)

**💬 Questions? Need Packet Tracer files? Feel free to reach out!**




[⬅️ Previous Project](01-MINI-BRANCH-README.md) | [🏠 Back to Main](README.md) | [➡️ Next Project](03-HQ-NETWORK-README.md)

**Made with ❤️ by Abdul Wahid**

</div>
