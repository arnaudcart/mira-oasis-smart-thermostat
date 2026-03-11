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

```
Nextion Touchscreen
        ↓
ESP32-S3 (ESPHome API)
        ↓
Home Assistant Scripts
        ↓
ESPHome IR Climate Entity
        ↓
IR Blaster → AC Unit
```

**Component roles**

- The **Nextion screen** acts purely as the user interface
- **Home Assistant** handles thermostat logic and system state
- The **IR blaster** sends commands directly to the AC unit

---

## Repository Structure

```
firmware/
  esphome/
    ui-controller.yaml
    ir-blaster.yaml

hardware/
  nextion-thermostat.md
  ir-blaster.md

docs/
  home-assistant-minimum.md
  home-assistant-scripts.md
  zigbee2mqtt-sonoff.md
```

**firmware**  
ESPHome configurations for the thermostat UI controller and IR blaster.

**hardware**  
Details about the physical thermostat build and IR hardware.

**docs**  
Home Assistant configuration and supporting documentation.

---

## UI Preview

Real screenshots of the working Nextion thermostat UI.

![Thermostat main screen](https://github.com/user-attachments/assets/0890588f-4f79-4d18-b8fa-fbde8dcd0186)

![Thermostat operation screen](https://github.com/user-attachments/assets/b0a77502-3227-4d96-ba90-27e7c3d74709)

---

## License

MIT
