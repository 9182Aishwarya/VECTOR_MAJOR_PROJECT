# VECTOR_MAJOR_PROJECT
# 🚗 Real-Time Vehicle Status Monitoring using CAN Protocol

A microcontroller-based embedded system that simulates real-time vehicle status monitoring using the **Controller Area Network (CAN)** protocol. Built with the **LPC2129 ARM7** microcontroller, this project demonstrates inter-node communication between the **Main**, **Indicator**, and **Fuel** modules over a CAN bus.

---

## 🔧 Hardware Components

- **LPC2129 (ARM7) Microcontroller** – Core processing unit for all nodes  
- **MCP2551** – CAN transceiver to enable communication between nodes  
- **MMA7660 Accelerometer** – Detects movement or crash impact  
- **16x2 Alphanumeric LCD** – Displays status information at the main node  
- **Analog Fuel Sensor (via ADC)** – Reads and reports fuel level  
- **Push Buttons (SW1 & SW2)** – Controls left/right indicators  
- **USB to UART Converter** – For serial communication and debugging

---

## 💻 Software & Tools

- **Keil µVision IDE** – Code development using Embedded C  
- **Flash Magic** – Flashing program to the LPC2129  
- **Proteus** *(Optional)* – For simulation of circuit and CAN communication  
- **Git & GitHub** – Version control and collaboration  

---

## 🧠 System Overview

### Node Roles:

- **Indicator Node**  
  - SW1: Send CAN frame for left indicator  
  - SW2: Send CAN frame for right indicator  
  - Real-time override: pressing either switch updates immediately

- **Fuel Node**  
  - Monitors fuel levels using ADC  
  - Sends fuel data over CAN periodically

- **Main Node**  
  - Receives CAN data from other nodes  
  - Displays status (indicators, fuel, acceleration) on LCD

---

## 🗂 Project Structure

├── MAIN_NODE.c # Main node logic (LCD display, CAN RX)
├── INDICATOR_NODE.c # Switch input and CAN TX logic
├── FUEL_NODE.c # Fuel level monitoring and CAN TX
├── adc.c / adc.h # ADC setup for analog sensors
├── can.c / can.h # CAN protocol configuration and frame handling
├── lcd.c / lcd.h # 16x2 LCD interfacing
├── delay.c / delay.h # Delay functions (ms/us)
├── i2c.c / i2c.h # I2C drivers (if used)
├── interrupt.c / .h # External interrupt configurations
├── README.md # This file


---

## ⚙️ How It Works

1. **Switch 1 Pressed:** Sends CAN frame to indicate *Left Turn*
2. **Switch 2 Pressed:** Sends CAN frame to indicate *Right Turn*
3. **Fuel Node:** Reads analog fuel level, sends value to main node
4. **Accelerometer (Optional):** Sends alert if abrupt motion detected
5. **Main Node:** Collects all CAN messages and updates the LCD

---

## 📸 Visuals (Optional)

Add:
- Circuit diagrams (Proteus or hand-drawn)
- Screenshots of LCD output or serial console
- Images of hardware setup

---

## 🧪 Test Cases

| Action              | Expected Result               |
|---------------------|-------------------------------|
| Press SW1           | LCD shows "Left Indicator ON" |
| Press SW2           | LCD shows "Right Indicator ON"|
| Low fuel            | LCD shows "Fuel Low"          |
| Crash detected      | LCD shows "Crash Detected!"   |

---

## 📜 License

This project is intended for **academic, educational, and personal use** only.  
Feel free to fork and experiment with the code.

---

## 🙌 Acknowledgements

- Developed as part of Embedded Systems course at Vector India  
- Inspired by real-time automotive safety systems  
- Special thanks to mentors and peers who guided development

---
