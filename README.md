# MIL-STD-461G Compliant BLDC Motor Driver

![Project Status](https://img.shields.io/badge/Status-Work_in_Progress-orange)
![Hardware](https://img.shields.io/badge/Hardware-Altium_Designer-blue)

## Project Overview
This repository contains the hardware design for a high-reliability, **28V 3-phase Brushless DC (BLDC)** motor controller. The project is specifically engineered for defense applications, with a primary focus on **MIL-STD-461G** EMI/EMC compliance and robust power management.

## Key Technical Specifications
* **Power Stage**: 3-Phase Inverter topology designed for a 28V (18V-32V operating range) nominal bus.
* **Control Architecture**: Implementation of Field Oriented Control (FOC) utilizing Space Vector PWM (SVPWM).
* **EMI & Protection**: 
    * Pi-type **EMI filter** tailored for MIL-STD-461G requirements.
    * **Ideal Diode** implementation for high-efficiency reverse polarity protection.
    * TVS diodes for transient voltage suppression.
* **Communication**: On-board isolated **CAN** bus and **RS422** differential encoder receiver.

## Core Component Breakdown
| Function | Component | Description |
| :--- | :--- | :--- |
| **Main MCU** | STM32G474 | Cortex-M4 with CORDIC math accelerator for optimized FOC. |
| **Gate Driver** | DRV8353 | 3-phase smart gate driver with integrated protection. |
| **Current Sense** | INA240 | In-line phase current sensing amplifiers (x3). |
| **Power Rails** | LM5005 & TPS54302 | Buck converters for 28V to 12V and 3.3V power distribution. |

## Schematic Previews
*Note: The schematic design phase is completed. Visuals represent the current hardware architecture.*

### Power Stage & EMI Filtering
![Power Stage](images/power_stage.png)
*28V Bus input, Pi-type EMI filter, and 3-phase inverter section.*

### Control Logic & Interfaces
![Control Logic](images/control_logic.png)
*STM32G474 MCU integration with isolated CAN and RS422 communication.*

## 🚀 Development Roadmap
- [x] **System Architecture & Component Selection**
- [x] **Schematic Design** (Power, MCU, and Interfaces)
- [ ] **PCB Layout** (Active Phase - Focusing on EMI and Thermal rules)
- [ ] **Hardware Manufacturing & Bring-up**
- [ ] **Firmware Development (FOC Implementation)**

## Author
**Enver Gökay ÇAY**
Electrical and Electronics Engineer | Karadeniz Technical University
