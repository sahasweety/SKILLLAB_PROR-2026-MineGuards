# 🪖 FPGA-Based Smart Gas Detection Helmet (Bluetooth Enabled)

---

# 📌 Project Overview

## Problem Statement

Underground mines are dangerous environments where workers are exposed to hazardous gases, high temperature, humidity variations, and emergency situations. Traditional monitoring systems are often expensive, limited in mobility, or dependent on centralized infrastructure.

This project aims to build a **real-time FPGA-based smart safety helmet system** capable of monitoring environmental conditions and transmitting alerts wirelessly.

---

## Proposed Solution

The proposed system uses an FPGA programmed entirely in **Verilog RTL** to monitor:

- Hazardous gas levels
- Temperature
- Humidity
- Emergency SOS trigger

The system provides:
- Real-time local alerts using LEDs
- Sensor data display on 7-segment displays
- Wireless communication through Bluetooth UART

The design avoids the use of processors or MicroBlaze and instead uses hardware-level FSM-based implementation.

---

# 🎯 Objectives

- Detect hazardous gas levels using MQ sensor
- Monitor temperature and humidity using DHT11
- Provide emergency alert using touch sensor
- Display real-time data on FPGA board (LED + 7-seg)
- Transmit sensor data wirelessly via Bluetooth (UART)

---

# 🧩 System Architecture

```text
MQ Sensor (Digital) ─┐
                     │
DHT11 Sensor ────────┼──> FPGA (Verilog RTL) ──> UART TX ──> Bluetooth ──> PC (MATLAB)
                     │
Touch Sensor ────────┘
                         ├──> LEDs (Gas Alert)
                         └──> 7-Segment Display (Temp & Humidity)
```

---

# ⚙️ Features

- Pure **Verilog RTL implementation**
- No soft-core processor (no MicroBlaze)
- **UART transmission (9600 baud)**
- **DHT11 protocol implemented using FSM**
- **Real-time display on 7-segment**
- **LED-based hazard indication**
- Compatible with **Bluetooth modules (HC-05)**

---

# 🔧 Hardware Requirements

| Component | Purpose |
|---|---|
| FPGA Board (Boolean Board / Xilinx FPGA) | Main processing unit |
| HC-05 Bluetooth Module | Wireless UART communication |
| MQ Gas Sensor | Hazardous gas detection |
| DHT11 Sensor | Temperature & humidity monitoring |
| Touch Sensor | Emergency SOS trigger |
| LEDs | Hazard indication |
| 7-Segment Display | Real-time display |
| Power Supply | System power |

---

# 🧠 Functional Description

## 1. Gas Detection

- MQ sensor provides digital output
- FPGA continuously monitors gas status
- LED turns ON when hazardous gas detected

---

## 2. Temperature & Humidity Monitoring

- DHT11 sensor uses custom single-wire protocol
- FSM-based Verilog controller implemented
- Temperature and humidity values extracted

---

## 3. Emergency Input

- Touch sensor acts as SOS trigger
- Emergency status sent through UART

---

## 4. Display System

- Temperature and humidity converted into BCD
- Displayed on 7-segment display

---

## 5. UART Transmission

Data sent every 1 second using UART.

### UART Output Format

```text
TEMP:25 HUM:60 GAS:1 SOS:0
```

---

# 📡 Communication Protocols

| Component | Protocol |
|---|---|
| MQ Sensor | Digital GPIO |
| DHT11 | Single-wire custom protocol |
| Bluetooth (HC-05) | UART Serial (9600 baud) |

---

# 🧱 FPGA Design

## Modules Included

| Module | Function |
|---|---|
| `top.v` | Top-level integration |
| `uart_tx.v` | UART transmitter |
| `dht11_controller.v` | Sensor interface FSM |
| `gas_detector.v` | Digital input logic |
| `touch_input.v` | SOS trigger |
| `data_formatter.v` | ASCII conversion |
| `seven_seg_driver.v` | Display control |
| `clock_divider.v` | Timing generation |

---

# 🔌 Pin Configuration (PMOD A)

| Pin | Function |
|---|---|
| A14 | DHT11 Data |
| B14 | MQ Sensor DOUT |
| A13 | Touch Sensor |
| B13 | UART TX |
| C14 | Reserved |
| C13 | Reserved |
| D12 | Reserved |
| E12 | Reserved |

---

# 🧾 Constraints File (XDC)

Includes:

- Clock input (100 MHz)
- PMOD pin mapping
- LED outputs
- 7-segment display pins

*(Refer to `constraints.xdc` in repository)*

---

# 🖥️ UART Output Example

```text
TEMP:27 HUM:65 GAS:0 SOS:0
TEMP:30 HUM:70 GAS:1 SOS:0
```

---

# 🚨 Alert Mechanism

| Condition | Action |
|---|---|
| Gas Detected | LED ON |
| Touch Activated | SOS transmitted through UART |
| Normal Condition | Continuous monitoring |

---

# ⚠️ Limitations

- MQ sensor used in digital mode only
- Bluetooth range limited underground
- DHT11 has limited accuracy and slow response time

---

# 🚀 Future Improvements

- Add LoRa for long-range communication
- Use analog gas sensing with ADC
- Integrate mesh networking
- Add data logging and cloud connectivity

---

# 🛠 Software & Tools Used

| Tool | Purpose |
|---|---|
| Verilog HDL | RTL Design |
| Vivado | FPGA Development |
| MATLAB Serial Monitor | UART Monitoring |

---

# 📅 Weekly Progress Log

| Week | Work Completed | Status |
|---|---|---|
| Week 1 | Project idea finalization and architecture planning | ✅ Completed |
| Week 2 | Sensor selection and hardware study | ✅ Completed |
| Week 3 | UART transmitter design in Verilog | ✅ Completed |
| Week 4 | DHT11 FSM implementation | 🔄 In Progress |
| Week 5 | FPGA integration and testing | ⏳ Pending |
| Week 6 | Bluetooth communication testing | ⏳ Pending |
| Week 7 | Final hardware testing and debugging | ⏳ Pending |
| Week 8 | Documentation and presentation | ⏳ Pending |

---

# 📌 Task Status

| Task | Status |
|---|---|
| System Design | ✅ Completed |
| Verilog RTL Coding | 🔄 In Progress |
| Sensor Interfacing | 🔄 In Progress |
| UART Communication | ✅ Completed |
| Bluetooth Integration | ⏳ Pending |
| Hardware Testing | ⏳ Pending |
| Documentation | 🔄 In Progress |

---

# 📷 Images / Screenshots

## Block Diagram
Not applicable currently. Diagram will be added after hardware implementation.

## Hardware Setup
Not applicable currently. Hardware assembly in progress.

## Simulation Results
Not applicable currently. Vivado simulation screenshots will be added later.

## Demo Video
Not applicable currently. Demo video will be uploaded after project completion.

---

# 🔗 Useful Links

- Vivado Design Suite: https://www.xilinx.com/products/design-tools/vivado.html
- Verilog HDL Reference: https://www.chipverify.com/verilog/verilog-tutorial
- DHT11 Datasheet: https://components101.com/sites/default/files/component_datasheet/DHT11%20Sensor%20Datasheet.pdf
- HC-05 Bluetooth Module: https://components101.com/wireless/hc-05-bluetooth-module

---

# 🧠 Viva Key Point

> “The system is implemented entirely in Verilog without a processor, using FSM-based sensor interfacing and UART communication to achieve a real-time embedded monitoring system on FPGA.”

---

# 📜 License

This project is for academic and research purposes.

---

# 👨‍💻 Team Members

| Name | Role |
|---|---|
| Pranay Wani | FPGA RTL Design |
| Ashutosh Tiwari | Sensor Interfacing |
| Vedant Naik | UART & Bluetooth Communication |
| Sweety Saha | Documentation & Testing |

---

# 📚 References

- DHT11 Sensor Datasheet
- Xilinx Vivado Documentation
- UART Communication Protocol
- Verilog HDL Design References

README organization and documentation practices are aligned with commonly recommended GitHub project documentation structures. :contentReference[oaicite:0]{index=0}
