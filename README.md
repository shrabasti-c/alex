# 🤖 Alex – Search & Rescue Robot
<p style="display: flex; align-items: flex-start;">
  <img src="https://github.com/user-attachments/assets/80429d12-ab4e-4a8c-8464-0bb663dc3abc" 
       style="height: 300px; width: auto;" />
  <img src="https://github.com/user-attachments/assets/fbe9bf5b-70a5-406d-bd1c-a3f49f36de56" 
       style="height: 300px; width: auto; margin-left: 10px;" />
</p>



Alex is a modular search-and-rescue robot designed to operate in environments that are unsafe or inaccessible to humans. It integrates advanced navigation, sensing, and manipulation capabilities to locate, triage, and assist “victims” in a simulated rescue mission.  

---

## 🌟 Features

- 🚀 **Autonomous & Remote-Controlled Operation**  
  Operates via secure remote communication or autonomously using SLAM-based navigation.  

- 🗺️ **Obstacle Detection & Mapping**  
  Combines LiDAR and ultrasonic sensors for real-time environment mapping and collision avoidance.  

- 🎨 **Color-Based Triage Simulation**  
  Distinguishes between red and green “astronauts” to simulate injured vs. healthy victims.  

- 🏥 **Rescue Actions**  
  - Deliver med packs to green astronauts ✅  
  - Drag red astronauts to safety using a robotic arm ⛑️  

- 🔋 **Energy-Efficient Design**  
  Dual power bank system ensures stable operation for motors, sensors, and computation.  

- 💡 **Affordable & Modular**  
  Built with widely available components for scalable, low-cost deployment.  

---

## 🏗️ Hardware Architecture
<img width="1133" height="737" alt="image" src="https://github.com/user-attachments/assets/c415e985-c67b-4e31-9237-e354de7e4748" />


| Component | Role |
|-----------|------|
| **Arduino Uno** | Handles low-level motor control, wheel encoders, and servo actuation. Compact and power-efficient. |
| **ESP32 Dev Board** | Interfaces with ultrasonic and color sensors; communicates with Raspberry Pi. |
| **Raspberry Pi** | Central processing unit; runs SLAM, LiDAR mapping, path planning, and web server. |
| **LiDAR System** | Real-time mapping & obstacle detection for autonomous navigation. |
| **Robotic Arm** | Simple manipulator (servo motors + ice cream sticks) to drag red astronauts. |
| **Med Pack Dispenser** | Servo-controlled modified Coke can to deliver aid to green astronauts. |
| **Power Management** | Dual power banks + PD trigger board for stable voltage to all components. |

---

## 🛠️ Firmware Overview

### Arduino Uno
- Executes low-level movement & servo commands  
- Monitors wheel encoders for precise odometry  
- Serial communication with Raspberry Pi  
- Interrupt-driven encoder tracking  
- Motor control via Adafruit Motor Shield  

### ESP32
- Reads TCS3200 color sensor 🎨  
- Measures distances with HC-SR04 ultrasonic sensors 📏  
- Sends sensor data to Raspberry Pi via Wi-Fi 🌐  

### Raspberry Pi
- Runs SLAM for real-time mapping 🗺️  
- Processes LiDAR and sensor data for navigation  
- Hosts web interface for remote control 💻  

---

## 🎯 Mission Scenario

Alex is designed as a three-chassis robot for a triage-style rescue simulation:  

1. Detect **green astronaut** → deliver med pack ✅  
2. Detect **red astronaut** → drag back to starting point ⛑️  

This mirrors real-world disaster-response operations where triage and targeted actions are critical.  

---

## ⚡ Power & Stability Design

- **PD Trigger Board:** Stable voltage output (9V, 12V) for high-power components  
- **Separate Power Supplies:**  
  - Servo motors + Raspberry Pi ✅  
  - Motor driver powered independently ⚡  
- **Energy Efficiency:** Arduino Uno chosen for low power consumption 🔋  

---

## 📝 Installation & Setup

1. Connect Arduino Uno, ESP32, Raspberry Pi, and sensors per wiring diagram 🔌  
2. Flash Arduino Uno firmware for motor & encoder control  
3. Upload ESP32 firmware for color & distance sensors  
4. Run SLAM + control software on Raspberry Pi 🖥️  
5. Access web interface to monitor status & send remote commands 🌐  

---

## 🌍 Potential Applications
- Search-and-rescue training simulations  
- Disaster-response prototyping in hazardous environments  
- Low-cost robotic systems for triage & targeted aid delivery 
