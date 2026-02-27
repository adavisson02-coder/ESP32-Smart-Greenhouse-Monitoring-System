# ENGR 4321 Project 1 – Smart Greenhouse Monitoring System (ESP32)

**Course:** ENGR 4321 Microcontrollers & Embedded Systems  
**Student:** Austin Davisson  
**Project Type:** IoT + Cloud Monitoring (Wokwi Simulation + Hardware Build)

## Overview
This project implements a Smart Greenhouse Monitoring System using an ESP32. The system measures:
- Temperature & Humidity (DHT11 / DHT22 in simulation)
- Light Level (photoresistor / LDR on ADC)
- Soil Moisture (potentiometer or soil sensor on ADC)

Sensor data is published to **Adafruit IO** using **WiFi + MQTT**, and the system triggers local alerts using an **LED** and **buzzer** when conditions exceed defined thresholds.

## Features
- ESP32 sensor acquisition (DHT + ADC)
- WiFi connection and MQTT publishing to Adafruit IO
- JSON feed publishing for logging/debugging
- Status logic with thresholds (OK / WARN / ALERT)
- LED and buzzer alert outputs

## System Logic (Thresholds)
- **ALERT:** Soil dry OR Temperature too high → LED ON + buzzer beep
- **WARN:** Low humidity OR Low light → LED indicator only
- **OK:** All conditions normal → LED OFF

## Wokwi Simulation
This repository includes the Wokwi simulation files in `/wokwi`.

**How to run:**
1. Open the Wokwi project (link below)  
2. Start simulation  
3. View Serial Monitor output  
4. Confirm Adafruit IO dashboard updates

**Wokwi Project Link:** *(paste your Wokwi share link here)*

## Adafruit IO Setup
Feeds used:
- `temp`
- `hum`
- `light`
- `soil`
- `status`
- `json`

Dashboard blocks:
- Gauges: temp, hum, light, soil
- Text: status (and optional json)

## Pinout (Hardware Build)
| Device | ESP32 Pin |
|---|---|
| DHT DATA | GPIO 13 |
| LDR (divider midpoint) | GPIO 34 |
| Soil sensor/pot | GPIO 35 |
| LED | GPIO 18 |
| Buzzer | GPIO 19 |

## Screenshots
| Simulation Wiring | Serial Monitor | Adafruit Dashboard | Hardware |
|---|---|---|---|
| ![Simulation](docs/images/simulation_wiring.png) | ![Serial](docs/images/serial_monitor.png) | ![Dashboard](docs/images/adafruit_dashboard.png) | ![Hardware](docs/images/hardware_build.jpg) |

## Report
The final report used for submission is located in:
`docs/report/`

## License
MIT License (see `LICENSE`).
