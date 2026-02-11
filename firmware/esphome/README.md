# ESPHome Firmware

This project uses **two ESPHome nodes** with Home Assistant as the control plane.

## 1) UI Controller (Nextion on ESP32-S3)
- File: `ui-controller.yaml`
- Reads Home Assistant entities (temperature, humidity, date/time, weather/icon state)
- Renders values on the Nextion display over UART
- Sends touch/button events back to Home Assistant by calling scripts

## 2) IR Blaster (ESP8266)
- File: `ir-blaster.yaml`
- Exposes a `midea_ir` climate entity in Home Assistant
- Transmits IR commands to the AC unit
- Periodically sends room temperature to AC via Midea "Follow Me" IR frames

## Configuration Tips
- Use `substitutions` at the top of each YAML to map your own entity IDs quickly.
- Keep real credentials and encryption keys only in `secrets.yaml` (never commit).
- Validate each config before flashing:

```bash
esphome config firmware/esphome/ui-controller.yaml
esphome config firmware/esphome/ir-blaster.yaml
```

## Secrets
Copy `secrets.example.yaml` to `secrets.yaml` locally and fill in your Wi-Fi and API secrets.
