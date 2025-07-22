# 🚘 Vehicle Status Monitoring via CAN – LPC2129 Project

This project simulates real-time communication between vehicle modules using the **CAN protocol** on an **LPC2129 (ARM7)** microcontroller. It demonstrates how embedded systems manage and monitor vehicle parameters like indicators, fuel level, and crash alerts.

---

## 🔩 What It Includes

- **Main Node** – Displays all received data on LCD  
- **Indicator Node** – Sends left/right turn commands  
- **Fuel Node** – Monitors and sends fuel level via ADC  
- **Accelerometer** – Detects crash/motion alerts  

---

## 🛠️ Hardware & Tools

- LPC2129, MCP2551, LM35/analog fuel sensor  
- 16x2 LCD, MMA7660 Accelerometer  
- Buttons (SW1, SW2), USB to UART  
- Keil IDE, Flash Magic

---

## 🚦 How It Works

- Button press → Sends CAN frame (left/right turn)  
- Fuel sensor → Sends fuel data to Main Node  
- Main Node → Updates LCD with latest info  
- Crash detected → Alert shown on LCD

---

## 📁 Files Overview

- `MAIN_NODE.c`, `INDICATOR_NODE.c`, `FUEL_NODE.c`  
- `can.c`, `adc.c`, `lcd.c`, `interrupt.c`  
- `README.md`

---

## ✅ Quick Test

| Trigger           | LCD Output               |
|------------------|--------------------------|
| Press SW1        | Left Indicator ON        |
| Fuel Low         | Fuel Level Low           |
| Crash Detected   | Crash Alert on LCD       |

---

## 📌 Notes

- Built for academic learning  
- Real-world inspired communication demo using CAN  
- Customize easily for automotive or IoT use cases

---

Made with 💡 by students of Vector India.
