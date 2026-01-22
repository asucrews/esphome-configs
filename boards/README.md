# Boards

Board-level ESPHome packages live here. These focus on the ESP32 family and
standardize the framework, logger, and flash write preferences so devices can
stay lightweight.

## Layout
- `boards/idf/` - ESP-IDF-based board definitions

## Usage
Reference a board package from a device config:

```yaml
packages:
  board: boards/idf/esp32dev.yaml
```

If you are consuming these from another repo, use the GitHub package form:

```yaml
packages:
  board: github://asucrews/esphome-configs/boards/idf/esp32dev.yaml@main
```

## Included defaults
- ESP-IDF framework
- `preferences.flash_write_interval: 1min`
- Logger enabled (some boards pin it to USB_SERIAL_JTAG)

## Available boards

| File | Board | Notes |
| --- | --- | --- |
| `boards/idf/esp32dev.yaml` | ESP32 DevKit/Dev Module | Baseline ESP32 ESP-IDF config. |
| `boards/idf/esp32_c3_devkitc_1.yaml` | ESP32-C3-DevKitC-1 (4MB) | BLE enabled, USB_SERIAL_JTAG logger. |
| `boards/idf/esp32_c6_devkitc_1.yaml` | ESP32-C6-DevKitC-1 (4MB) | BLE enabled, USB_SERIAL_JTAG logger. |
