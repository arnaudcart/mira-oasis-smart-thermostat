# Mira Oasis Smart Thermostat

A **DIY wall-mounted smart thermostat** for split AC units built with **ESPHome and Home Assistant**.

Designed and tested in **Mira Oasis villas (Dubai)** where AC units are typically controlled via **IR remotes** instead of traditional wired thermostats.

This project adds a **touchscreen thermostat interface** that integrates with **Home Assistant** while controlling the AC using **infrared commands**.

---

## Why this exists

Many villas in Mira Oasis use **split AC systems controlled by IR remotes**.

Because of this, traditional smart thermostats (Nest, Ecobee, etc.) usually **do not work well without major HVAC modifications**.

This project provides a simple DIY alternative:

- Wall-mounted touchscreen thermostat
- Full **Home Assistant integration**
- Uses inexpensive hardware (ESP32 + Nextion)
- Controls AC units using **IR commands**

---

## Key Components

- **Nextion touchscreen (4.3")** – wall-mounted thermostat interface  
- **ESP32-S3** – UI controller running ESPHome  
- **ESP8266 IR blaster** – sends commands to the AC unit  
- **Home Assistant** – handles thermostat logic and automations  
- **Zigbee temperature sensor** – provides room temperature  

The system is designed for **AC control (cooling only)** and has been **tested with the Midea IR protocol**.

---

## System Overview

The thermostat is split into independent components to keep the system **modular, reliable, and easy to extend**.
