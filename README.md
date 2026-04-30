# 1. Team Identity

## 1.1 Studio / Group Name

MineGuards

---

## 1.2 Team Members

| Name | Primary Role | Secondary Role | Strengths Brought to the Project |
|---|---|---|---|
| Pranay Wani | FPGA RTL Design / Coding | Documentation | Verilog Design, Problem Solving |
| Ashutosh Tiwari | Electronics / Hardware | Testing | Sensor Integration |
| Vedant Naik | Communication Module | Connection | UART & Bluetooth Integration |
| Sweety Sahya | Communication Module | Documentation | UART & Bluetooth Integration |
---

## 1.3 Project Title

**FPGA-Based Smart Gas Detection Helmet (Bluetooth Enabled)**

---

## 1.4 One-Line Pitch

A real-time FPGA-based smart safety helmet system for underground mine workers that detects hazardous gases, monitors environmental conditions, and sends wireless alerts using Bluetooth communication.

---

## 1.5 Expanded Project Idea

This project implements a smart mine safety helmet system using FPGA and pure Verilog RTL design without any processor or MicroBlaze. The system monitors hazardous gas levels, temperature, humidity, and emergency touch input to improve underground mine worker safety.

The system creates a real-time monitoring and alert experience where sensor data is processed directly by FPGA hardware and displayed through LEDs and 7-segment displays while also transmitting live data wirelessly using UART and Bluetooth communication. Technologies involved include Verilog HDL, FPGA design, UART communication, DHT11 protocol interfacing, gas sensing, and Bluetooth-based wireless transmission.

---

# 2. Inspiration

## 2.1 References

| Source Type | Title / Link | What Inspired You |
|---|---|---|
| Research | Mine safety monitoring systems | Real-time worker safety monitoring |
| YouTube | FPGA sensor interfacing tutorials | FPGA-based hardware implementation |
| Datasheets | DHT11 and HC-05 documentation | Sensor and communication protocols |

---

## 2.2 Original Twist

The project is implemented completely using pure Verilog RTL without using any processor or operating system. All sensor interfacing, UART communication, and display control are implemented directly in FPGA hardware using FSM-based logic.

---

# 3. Project Intent

## 3.1 User Journey

A mine worker wears the smart safety helmet while entering underground mining areas. The sensors continuously monitor environmental conditions such as gas concentration, temperature, and humidity. If hazardous gas is detected, the system immediately activates alert LEDs and sends warning data wirelessly through Bluetooth.

In emergency situations, the worker can press the touch sensor to trigger an SOS alert. The FPGA processes all sensor data in real time and transmits updates to an external monitoring system such as MATLAB serial monitor.

---

# 4. Definition of Success

## 4.1 Definition of “Usable”

The system is considered usable if it can successfully:

- Detect hazardous gas conditions
- Read temperature and humidity values
- Trigger emergency SOS alerts
- Display sensor data on FPGA board
- Transmit UART data wirelessly through Bluetooth

---

## 4.2 Minimum Usable Version

The minimum usable version includes:

- MQ gas sensor interfacing
- LED-based alert system
- UART transmission through HC-05
- Basic FPGA RTL implementation

---

## 4.3 Stretch Features

- LoRa communication
- Cloud monitoring dashboard
- GPS tracking
- Analog gas sensing with ADC
- Mesh networking

---

# 5. System Overview

## 5.1 Project Type

- Electronics-based
- Sensor-based
- App-connected
- Light-based
- Screen/UI-based
- Game logic based

---

## 5.2 High-Level System Description

The system receives input from MQ gas sensor, DHT11 sensor, and touch sensor. The FPGA processes the data using Verilog RTL modules and FSM-based control logic.

The processed output is displayed through LEDs and 7-segment displays while UART communication sends sensor data wirelessly through Bluetooth to a PC or MATLAB serial monitor.

---

## 5.3 Input / Output Map

| System Part | Type | What It Does |
|---|---|---|
| MQ Sensor | Input | Detects hazardous gas |
| DHT11 | Input | Reads temperature and humidity |
| Touch Sensor | Input | Emergency SOS trigger |
| FPGA | Processing | Processes sensor data |
| LEDs | Output | Hazard indication |
| 7-Segment Display | Output | Displays sensor values |
| HC-05 Bluetooth | Output | Wireless UART communication |

---

# 6. System Design, Sketches and Visual Planning

## 6.1 Concept Architecture/sketch/schematic

Not applicable currently. Architecture diagram will be added after hardware implementation.

---

## 6.2 Labeled Build Sketch/architecture/flow diagram/algorithm

Not applicable currently. Labeled hardware architecture will be added later.

---

## 6.3 Approximate Dimensions

| Dimension | Value |
|---|---|
| Length | 20 cm |
| Width | 18 cm |
| Height | 12 cm |
| Estimated weight | 500 g |

---

# 7. Electronics Planning

## 7.1 Electronics Used

| Component | Quantity | Purpose |
|---|---|---|
| FPGA Board | 1 | Main controller |
| HC-05 Bluetooth Module | 1 | UART communication |
| MQ Gas Sensor | 1 | Gas detection |
| DHT11 Sensor | 1 | Temperature & humidity monitoring |
| Touch Sensor | 1 | SOS emergency input |
| LEDs | Multiple | Hazard indication |
| 7-Segment Display | 2 | Display sensor values |

---

## 7.2 Wiring Plan

The MQ gas sensor, DHT11 sensor, and touch sensor are connected to FPGA PMOD pins. The HC-05 Bluetooth module is connected through UART TX communication.

The FPGA processes all incoming sensor signals and generates output signals for LEDs, 7-segment display, and UART transmission.

All modules share common ground and are powered using FPGA board power supply.

---

## 7.3 Circuit Diagram/architecture diagram

Not applicable currently. Circuit diagram will be added after final hardware wiring.

---

## 7.4 Power Plan

| Question | Response |
|---|---|
| Power source | FPGA Board Power Supply |
| Voltage required | 3.3V / 5V |
| Current concerns | Stable sensor operation |
| Safety concerns | Avoid short circuits and loose wiring |

---

# 8. Software Planning

## 8.1 Software Tools

| Tool / Platform | Purpose |
|---|---|
| Verilog HDL | FPGA RTL Design |
| Vivado | FPGA development |
| MATLAB Serial Monitor | UART data monitoring |

---

## 8.2 Software Logic/Algorithm

Startup behavior:  
The FPGA initializes UART communication, display drivers, and sensor interfaces.

Input handling:  
The system continuously reads data from MQ sensor, DHT11 sensor, and touch sensor.

Decision logic:  
If gas is detected or SOS trigger is activated, the FPGA generates alert outputs.

Output behavior:  
The system activates LEDs, updates 7-segment display, and sends UART messages through Bluetooth.

Reset behavior:  
The FPGA resets sensor values and returns to monitoring state.

---

## 8.3 Code Flowchart

Not applicable currently. Flowchart will be added later.

---

# 9. Bill of Materials
Not Applicable

## 9.1 Full BOM
Not Applicable


---

## 9.2 Material Justification

FPGA was selected because the project focuses on hardware-level implementation using Verilog RTL. MQ sensor was selected for hazardous gas detection, while DHT11 was selected for low-cost environmental monitoring.

HC-05 Bluetooth module was selected for simple UART-based wireless communication.

---

## 9.3 Items You Chose

| Item | Why Needed | Status |
|---|---|---|
| MQ Sensor | Hazard detection | Received |
| DHT11 Sensor | Temperature monitoring | Received |
| HC-05 | Wireless communication | Received |

---

## 9.4 Budget Summary

Not Applicable
---

## 9.5 Budget Reflection

Not Applicable

---

# 10. Planning the Work

## 10.1 Team Working Agreement

Tasks are divided based on electronics, coding, testing, and documentation responsibilities.

Progress is checked regularly through team discussions and hardware testing sessions. Documentation is updated after every major implementation stage.

---

## 10.2 Task Breakdown

| Task ID | Task | Owner | Status |
|---|---|---|---|
| T1 | System Architecture |  | Completed |
| T2 | UART Design |  | Completed |
| T3 | DHT11 Interfacing | | In Progress |
| T4 | Bluetooth Integration |  | Pending |

---

## 10.3 Responsibility Split

| Area | Main Owner | Support Owner |
|---|---|---|
| FPGA RTL Design |  |  |
| Electronics |  |  |
| Documentation |  |  |
| Testing |  |  |

---

# 11 Hour Milestones

## 11.1 8-hour Plan

### Bi Hour 1 — Plan and De-risk

- System architecture finalized
- Sensor selection completed
- BOM prepared

### Bi Hour 2 — Build Subsystems

- UART module designed
- DHT11 FSM started
- Sensor testing completed

### Bi Hour 3 — Integrate

- FPGA modules integrated
- UART communication tested

### Bi Hour 4 — Refine and Finish

- Debugging
- Documentation
- Final testing

---

## 11.2 Update Log

Not Applicable
---

# 13. Risks and Unknowns

## 13.1 Risk Register

| Risk | Type | Likelihood | Impact | Mitigation Plan |
|---|---|---|---|---|
| Sensor timing issues | Technical | Medium | High | Debug using simulation |
| Bluetooth communication failure | Technical | Medium | Medium | Test UART independently |

---

## 13.2 Biggest Unknown Right Now

The biggest uncertainty is stable real-time sensor interfacing and wireless communication integration on FPGA hardware.

---

# 14. Testing

## 14.1 Technical Testing Plan

| What Needs Testing | How You Will Test It | Success Condition |
|---|---|---|
| UART Communication | Monitor serial output | Correct UART transmission |
| Gas Detection | Trigger MQ sensor | LED and UART alert generated |
| DHT11 Reading | Compare sensor output | Correct temperature display |

---

## 14.2 Testing and Debugging Log

| Date | Problem Found | Result |
|---|---|---|
| 30 April | UART baud mismatch | Fixed |
| 2 April | Sensor timing issue | Debugging in progress |

---

## 14.3 Playtesting Notes

| Tester | What They Enjoyed | What Needs Improvement |
|---|---|---|
| Team Members | Real-time monitoring | Faster wireless range |

---

# 15. Build Documentation

## 15.1 Fabrication Process

The project involves FPGA hardware integration, sensor wiring, and display interfacing. Components are connected using PMOD pins and breadboard-based prototyping.

The hardware setup is continuously revised during testing and debugging stages.

---

# 16. Build Photos

Not applicable currently. Build photos will be added after hardware assembly.

---

# 17. Final Outcome

## 17.1 Final Description

The final system is an FPGA-based smart safety helmet capable of detecting hazardous gas conditions, monitoring temperature and humidity, generating emergency alerts, and transmitting data wirelessly using Bluetooth communication.

---

## 17.2 What Works Well

- UART communication
- FPGA RTL implementation
- Gas alert indication

---

## 17.3 What Still Needs Improvement

- Wireless range
- Sensor response optimization

---

## 17.4 What Changed From the Original Plan

Initially the project focused only on gas monitoring, but later temperature, humidity, and SOS emergency functionality were added.

---

# 18. Reflection

## 18.1 Team Reflection

The team worked well in FPGA design and hardware planning. Sensor timing and debugging slowed development slightly.

---

## 18.2 Technical Reflection

The project helped improve understanding of:

- FPGA design
- Verilog RTL
- UART communication
- Sensor interfacing
- Real-time embedded systems

---

## 18.3 Design Reflection

We learned the importance of hardware planning, debugging, modular design, and real-time system integration.

---

## 18.4 If You Had One More Hour

We would improve wireless communication range and add cloud-based monitoring.

---

# 19. Final Submission Checklist

- Team details are complete
- Project description is complete
- Inspiration sources are included
- BOM is complete
- Budget summary is complete
- Task breakdown is complete
- Testing log is updated
- Reflection is written
