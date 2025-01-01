# Testing Document: TPMS, HVAC, and BCM for Zonal Architecture  

## 1. Overview  
This section outlines the testing procedures, test cases, and validation methods used to ensure the correct functionality and reliability of the integrated TPMS, HVAC, and BCM system within a zonal architecture.  

---

## 2. Testing Phases  

### 2.1 Phase 1: Unit Testing  
- **Objective**: Test individual components and modules to ensure they meet design requirements.  
- **Components Tested**:  
  1. Tire Pressure Sensors  
  2. Temperature Sensors  
  3. LEDs for indicating thresholds  
  4. Microcontroller inputs and outputs  

#### Example Test Case: Sensor Functionality  
- **Input**: Simulate pressure values (e.g., 25 PSI, 30 PSI, 35 PSI).  
- **Expected Output**:  
  - LED blinks if pressure is below 30 PSI.  
  - LED remains off for values above 30 PSI.  
- **Result**: Pass/Fail  

---

### 2.2 Phase 2: Integration Testing  
- **Objective**: Validate the interaction between different modules (TPMS, HVAC, and BCM).  
- **Steps**:  
  1. Connect tire pressure and temperature sensors to microcontroller.  
  2. Test inter-zone communication for data consistency.  
  3. Simulate multiple zones operating simultaneously.  

#### Example Test Case: Zonal Communication  
- **Input**: Simulated temperature inputs from all zones (e.g., Zone 1: 25°C, Zone 2: 35°C).  
- **Expected Output**:  
  - Master controller receives accurate data from all zones.  
  - LED indications reflect correct zonal states.  
- **Result**: Pass/Fail  

---

### 2.3 Phase 3: System Testing  
- **Objective**: Test the system as a whole to validate end-to-end functionality.  
- **Steps**:  
  1. Simulate real-world scenarios using Simulink.  
  2. Monitor system behavior during high-load conditions.  
  3. Test fault detection and fault isolation mechanisms.  

#### Example Test Case: Fault Isolation  
- **Input**: Introduce a fault in one zone (e.g., disconnect a sensor).  
- **Expected Output**:  
  - Fault is isolated to the specific zone.  
  - Other zones continue to operate normally.  
- **Result**: Pass/Fail  

---

### 2.4 Phase 4: Performance Testing  
- **Objective**: Assess system performance under varying conditions.  
- **Metrics Evaluated**:  
  1. Response time to sensor input.  
  2. Energy consumption of the system.  
  3. Reliability under long-term operation.  

#### Example Test Case: Response Time  
- **Input**: Change pressure value suddenly from 35 PSI to 25 PSI.  
- **Expected Output**: LED response within 1 second.  
- **Result**: Pass/Fail  

---

## 3. Tools Used for Testing  
1. **Tinkercad**: Simulating hardware components and validating circuit behavior.  
2. **Simulink**: Testing control logic and system-level performance.  
3. **Multimeter and Oscilloscope**: Verifying sensor outputs and microcontroller signals.  
4. **Arduino IDE Serial Monitor**: Monitoring real-time data during hardware testing.  

---

## 4. Challenges Encountered During Testing  
- **Sensor Noise**: Calibrated sensors to minimize errors in noisy environments.  
- **Communication Delays**: Optimized protocols to ensure low-latency inter-zone communication.  
- **Fault Simulation**: Introduced controlled faults to test system reliability.  

---

## 5. Conclusion  
The system passed all major test cases, validating the functionality of TPMS, HVAC, and BCM within a zonal architecture. The prototype is ready for further enhancements or deployment in larger-scale applications.  


