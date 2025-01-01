# Design Document: TPMS, HVAC, and BCM for Zonal Architecture  

## 1. High-Level Design (HLD)  

### 1.1 Zonal Architecture  
- The system is divided into **zones**, each responsible for specific tasks such as tire pressure monitoring (TPMS), heating, ventilation, and air conditioning (HVAC), and body control module (BCM) functionalities.  
- A **master controller** communicates with each zone to gather data and coordinate responses.  
- Each zone operates autonomously but shares data with the master for centralized decision-making.  

### 1.2 Communication Framework  
- **Wired Communication**: Use protocols like I2C or UART for data exchange between sensors, controllers, and the master unit.  
- **Fault Isolation**: Each zone has isolated communication, ensuring faults in one zone do not impact others.  

### 1.3 Control Mechanisms  
- Define **control thresholds** for parameters such as tire pressure (e.g., below 30 PSI) and temperature (e.g., 18°C–28°C for HVAC comfort range).  
- Implement a **feedback loop** to ensure real-time updates and actions based on sensor data.  

### 1.4 Prototyping and Simulation  
- **Simulation Tools**: Use Tinkercad for electronic circuit simulation and Simulink for system-level validation.  
- **Prototype**: Employ microcontrollers like Arduino and sensors for real-world testing.  
- Visual feedback via **LEDs** to indicate pressure and temperature status.  

---

## 2. Low-Level Design (LLD)  

### 2.1 Sensor Integration  
#### TPMS:  
- Use **pressure sensors** to monitor tire pressure.  
- Program LEDs to display:  
  - **Green**: Normal pressure.  
  - **Yellow**: Low pressure (warning).  
  - **Red**: Critical pressure.  

#### HVAC:  
- Use **temperature sensors** to monitor zonal temperatures.  
- Control LEDs to display:  
  - **Blue**: Low temperature.  
  - **Green**: Normal temperature.  
  - **Red**: High temperature.  

### 2.2 Control Logic  
#### TPMS Control Unit:  
- Read sensor data at regular intervals.  
- Compare pressure readings with predefined thresholds.  
- Activate LEDs or send alerts to the master controller in case of anomalies.  

#### HVAC Control Unit:  
- Monitor temperature levels and adjust HVAC settings automatically.  
- Use LED indicators to show deviations from the comfort range.  

#### BCM Control Unit:  
- Centralize control of body functions like lighting and alarms.  
- Interface with the master controller for seamless integration.  

### 2.3 Communication Protocols  
- **I2C**: For efficient sensor-to-controller communication.  
- **UART**: For controller-to-controller or zone-to-master communication.  

### 2.4 Prototype Components  
- **Microcontroller**: Arduino or STM32 for control units.  
- **Sensors**:  
  - Pressure sensors for TPMS.  
  - Temperature sensors for HVAC.  
- **LED Indicators**: Visual feedback for system states.  

---

## 3. Non-Functional Design Aspects  

### 3.1 Scalability  
- Zones can be expanded with minimal reconfiguration by adding new sensors or controllers.  

### 3.2 Reliability  
- Include error detection and recovery mechanisms to handle sensor failures or communication errors.  

### 3.3 Efficiency  
- Optimize energy consumption using low-power components and efficient algorithms.  

### 3.4 Maintainability  
- Modular design ensures that faulty zones can be isolated and replaced without impacting the entire system.  

### 3.5 Safety  
- Implement fail-safe mechanisms to prevent system damage or hazardous situations.  

---

## 4. Tools and Platforms  
- **Tinkercad**: For circuit simulation and prototyping.  
- **Simulink**: For system-level design and validation.  
- **GitHub**: For code versioning and documentation.  
- **Arduino IDE**: For programming microcontrollers.  

---

This design ensures an efficient, scalable, and reliable zonal architecture for TPMS, HVAC, and BCM functionalities. Let me know if you need additional details or modifications!  

