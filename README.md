# Smart Running Glasses

## Overview

Smart Running Glasses is a Senior Design project focused on developing lightweight wearable glasses that provide real-time running information directly within the runner's field of view.

The goal is to eliminate the need to constantly check a watch or phone while running by displaying key metrics through a HUD (Head-Up Display) system.

---

## Planned Features

* Real-time speed monitoring
* Distance tracking
* Heart rate monitoring
* Ambient temperature monitoring
* Running cadence analysis
* Battery monitoring
* Bluetooth Low Energy (BLE) connectivity
* HUD-based information display

Future possibilities:

* Navigation assistance
* Running analytics
* Workout modes
* Mobile application integration

---

## Current Hardware Stack

### Microcontroller

* ESP32 DevKit V1 (Prototype)
* ESP32-WROOM-32 (Future PCB)

### Sensors

* MAX30102 (Heart Rate Sensor)
* BME280 (Temperature, Humidity, Pressure)
* MPU6050 (Prototype IMU)
* BNO085/BNO086 (Future IMU)

### Positioning

* GPS Module (TBD)

### Display

* SSD1306 OLED (Prototype)
* Micro OLED HUD Display (Future)

---

## Communication Protocols

| Component          | Protocol |
| ------------------ | -------- |
| GPS                | UART     |
| MAX30102           | I2C      |
| BME280             | I2C      |
| MPU6050            | I2C      |
| OLED Display       | I2C      |
| Future IMU         | SPI      |
| Future HUD Display | SPI      |

---

## Software Stack

### Current

* Arduino C++
* GitHub
* Notion

### Future

* ESP-IDF
* Bluetooth Low Energy (BLE)
* Mobile Application Integration

---

## Development Roadmap

### Phase 1 — Summer 2026

* Learn ESP32
* Learn UART, I2C, SPI
* Test all sensors individually
* Build first working prototype
* Display speed, distance, heart rate, and temperature

### Phase 2 — Fall 2026

* Finalize hardware architecture
* Evaluate HUD options
* Design PCB schematic
* Begin PCB development

### Phase 3 — Spring 2027

* Manufacture PCB
* Integrate hardware into glasses frame
* Optimize battery life
* Final testing and validation

---

## Topics We Are Currently Researching

* HUD systems
* Micro OLED displays
* Waveguides
* Prism optics
* PCB design
* Battery management
* BLE communication
* Running analytics
* Wearable device ergonomics

---

## Team Goal

Build a functional wearable prototype capable of displaying:

* Speed
* Distance
* Heart Rate
* Temperature

while allowing the runner to keep their eyes focused on the road.

---

## Status

🚧 Early Research & Prototype Development
