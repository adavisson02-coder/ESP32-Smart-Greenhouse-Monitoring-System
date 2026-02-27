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
|<img width="679" height="432" alt="Screenshot 2026-02-27 at 4 33 17 PM" src="https://github.com/user-attachments/assets/8896d054-6831-47d4-a49d-9b112ee8ff71" />
| <img width="354" height="165" alt="Screenshot 2026-02-27 at 4 33 27 PM" src="https://github.com/user-attachments/assets/46583795-8ff1-4c49-998e-8d3545192036" />
 | <img width="1320" height="446" alt="Screenshot 2026-02-27 at 4 34 12 PM" src="https://github.com/user-attachments/assets/9d17e591-0dd4-43f5-a7eb-db9ac3eb2a5b" />
 |


## License
MIT License

Copyright (c) 2026 Austin Davisson

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
