# Smart Classroom Occupancy and Energy Saving System using STM32 Nucleo F446RE

## Overview

The Smart Classroom Occupancy and Energy Saving System is an embedded systems mini project developed using the STM32 Nucleo F446RE microcontroller. The system automatically controls classroom lighting and fan operation based on human occupancy and room temperature, thereby reducing unnecessary power consumption.

This project demonstrates the practical implementation of automation and energy management using sensors and relay modules.

---

## Features

- Automatic classroom occupancy detection using a PIR sensor.
- Automatic light control based on occupancy.
- Automatic fan control based on room temperature.
- Energy saving by switching OFF appliances when the classroom is empty.
- Implemented using STM32 HAL libraries.
- Developed using STM32CubeIDE.

---

## Components Used

| Component | Quantity |
|----------|----------|
| STM32 Nucleo F446RE | 1 |
| PIR Motion Sensor (HC-SR501) | 1 |
| KY-013 Temperature Sensor (10K NTC) | 1 |
| 1-Channel Relay Module | 2 |
| Breadboard | 1 |
| Jumper Wires | As required |
| USB Cable | 1 |

---

## Working Principle

1. The PIR sensor continuously detects human presence.
2. If no motion is detected:
   - Light OFF
   - Fan OFF
3. If motion is detected:
   - Light turns ON.
4. The temperature sensor measures classroom temperature.
5. If the measured temperature exceeds the preset threshold:
   - Fan turns ON.
6. When the classroom becomes empty:
   - Both light and fan are switched OFF automatically.

---

## Hardware Connections

### PIR Sensor

| PIR Pin | STM32 Pin |
|---------|-----------|
| VCC | 5V |
| GND | GND |
| OUT | PA0 |

---

### KY-013 Temperature Sensor

| KY-013 Pin | STM32 Pin |
|------------|-----------|
| + | 3.3V |
| - | GND |
| S | PA1 (ADC1_IN1) |

---

### Light Relay

| Relay Pin | STM32 Pin |
|-----------|-----------|
| VCC | 5V |
| GND | GND |
| IN | PB0 |

---

### Fan Relay

| Relay Pin | STM32 Pin |
|-----------|-----------|
| VCC | 5V |
| GND | GND |
| IN | PB1 |

---

## Software Requirements

- STM32CubeIDE
- STM32CubeMX
- STM32 HAL Library

---

## Development Environment

- Microcontroller: STM32F446RE
- IDE: STM32CubeIDE
- Language: Embedded C
- Framework: STM32 HAL

---

## Project Logic

```
Start

↓

Read PIR Sensor

↓

Motion Detected?

├── No
│     Light OFF
│     Fan OFF
│
└── Yes
      Light ON

      ↓

Read Temperature

↓

Temperature ≥ Threshold ?

├── Yes
│      Fan ON
│
└── No
       Fan OFF

↓

Repeat
```

---

## Pin Configuration

| STM32 Pin | Function |
|-----------|----------|
| PA0 | PIR Input |
| PA1 | Temperature Sensor (ADC) |
| PB0 | Light Relay |
| PB1 | Fan Relay |
| PB6 | I2C1 SCL (Reserved) |
| PB7 | I2C1 SDA (Reserved) |
| PA2 | USART2 TX |
| PA3 | USART2 RX |

---

## Advantages

- Saves electrical energy.
- Fully automatic operation.
- Low-cost implementation.
- Easy to install.
- Suitable for classrooms, offices and laboratories.

---

## Applications

- Smart Classrooms
- Conference Rooms
- Offices
- Laboratories
- Libraries
- Smart Buildings

---

## Future Improvements

- LCD or OLED display.
- IoT monitoring using ESP8266/ESP32.
- Mobile application.
- Wi-Fi based remote monitoring.
- Automatic attendance logging.
- Cloud data storage.
- Occupancy analytics dashboard.

---

## Project Structure

```
Core/
    Inc/
    Src/

Drivers/
STM32CubeMX.ioc

README.md
```

---

## Output

### Classroom Empty

- PIR = No Motion
- Light OFF
- Fan OFF

### Classroom Occupied

- PIR = Motion Detected
- Light ON

### Classroom Occupied & High Temperature

- PIR = Motion Detected
- Temperature > Threshold
- Light ON
- Fan ON

---

## Author

**Girivasan R**

Bachelor of Engineering (Electrical and Electronics Engineering)

Embedded Systems | STM32 | IoT | EV Technology

Output:
<img width="960" height="1280" alt="WhatsApp Image 2026-08-07 at 2 48 09 PM" src="https://github.com/user-attachments/assets/1ca35fc8-af7b-454f-84f1-b5a86893b970" />


---

## License

This project is developed for educational purposes.
