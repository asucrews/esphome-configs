# ESPHome Configs

Reusable ESPHome packages, boards, and device configs for personal use and sharing.

## Quick start
1. Start from a file in `devices/` or create a new device YAML.
2. Set the substitutions you need (see the table below).
3. Add shared secrets in `secrets.yaml`.
4. Include packages locally or via GitHub.

## Repository layout
- `boards/` - board and framework presets (ESP-IDF). See `boards/README.md`.
- `devices/` - device configs that assemble packages.
- `packages/` - reusable package fragments (api, wifi, BLE, sensors, etc.).

## Using the packages
You can include packages locally or via GitHub.

Local example:
```yaml
substitutions:
  device_name: "livingroom_sensor"
  device_friendly_name: "Living Room Sensor"
  area: "Living Room"
  wifi_ip_address: "192.168.1.50"
  wifi_auth_mode: "WPA2_PSK"
  timezone: "America/Chicago"
  ntp_server: "pool.ntp.org"

packages:
  board: ./boards/idf/esp32dev.yaml
  identity: ./packages/identity.yaml
  api: ./packages/api.yaml
  ota: ./packages/ota.yaml
  wifi: ./packages/wifi.yaml
  common: ./packages/common.yaml
```

GitHub example (used by the files in `devices/`):
```yaml
packages:
  identity: github://asucrews/esphome-configs/packages/identity.yaml@main
  board: github://asucrews/esphome-configs/boards/idf/esp32dev.yaml@main
  api: github://asucrews/esphome-configs/packages/api.yaml@main
  ota: github://asucrews/esphome-configs/packages/ota.yaml@main
  wifi: github://asucrews/esphome-configs/packages/wifi.yaml@main
  common: github://asucrews/esphome-configs/packages/common.yaml@main
```

## Package catalog

Core:
- `packages/identity.yaml`, `packages/identity_dio.yaml` - node identity (DIO variant forces flash mode).
- `packages/api.yaml` - encrypted ESPHome API.
- `packages/ota.yaml` - OTA password.
- `packages/wifi.yaml` - WiFi + captive portal.
- `packages/common.yaml` - uptime, WiFi signal, internal temp, restart buttons.
- `packages/time.yaml` - SNTP time sync.

Optional:
- `packages/ble.yaml` - BLE stack base.
- `packages/ble_proxy.yaml` - active BLE proxy with scan control.
- `packages/ble_tracker.yaml` - iBeacon config.
- `packages/api_ble_tracker.yaml` - API hooks to start/stop scans.
- `packages/i2c_bus_a.yaml` - I2C bus definition.
- `packages/status_led.yaml` - status LED output/light.
- `packages/sensors/bh1750_0x23.yaml` - BH1750 lux.
- `packages/sensors/shtcx_0x70.yaml` - SHTCx temperature/humidity.
- `packages/esp360_remote_tx.yaml` - RF/IR transmitter pins.
- `packages/esp360_remote_rx.yaml` - RF receiver (IR example commented).
- `packages/api_services/remote_tx.yaml` - API services to send RF/IR.

## Device configs
- `devices/template.yaml` - starter template for new devices.
- `devices/ratgdo-v25i.yaml` - ratgdo v2.5i.
- `devices/everything_presence_lite.yaml` - Everything Presence Lite.
- `devices/esp360_remote.yaml` - ESP360 remote hub (RF/IR).
- `devices/ble_tracker_c3.yaml` - BLE tracker on ESP32-C3.
- `devices/ble_tracker_c6.yaml` - BLE tracker on ESP32-C6.

## Substitutions used by packages
Set these in your device YAML (or in a shared file you include).

| Substitution | Used by | Purpose |
| --- | --- | --- |
| `device_name` | `packages/identity.yaml`, `packages/identity_dio.yaml` | ESPHome node name. |
| `device_friendly_name` | `packages/identity.yaml`, `packages/identity_dio.yaml` | Friendly name in HA. |
| `area` | `packages/identity.yaml`, `packages/identity_dio.yaml` | HA area assignment. |
| `wifi_ip_address` | `packages/wifi.yaml` | Static or DHCP target IP. |
| `wifi_auth_mode` | `packages/wifi.yaml` | Minimum WiFi auth mode. |
| `timezone` | `packages/time.yaml` | Time zone string. |
| `ntp_server` | `packages/time.yaml` | NTP server host. |
| `i2c_sda_pin` | `packages/i2c_bus_a.yaml` | I2C SDA pin. |
| `i2c_scl_pin` | `packages/i2c_bus_a.yaml` | I2C SCL pin. |
| `i2c_frequency` | `packages/i2c_bus_a.yaml` | I2C bus speed. |
| `status_led_pin` | `packages/status_led.yaml` | Status LED GPIO. |
| `ble_uuid` | `packages/ble_tracker.yaml` | BLE beacon UUID. |
| `ble_major` | `packages/ble_tracker.yaml` | BLE beacon major. |
| `ble_minor` | `packages/ble_tracker.yaml` | BLE beacon minor. |
| `rf_tx_pin` | `packages/esp360_remote_tx.yaml` | RF TX GPIO. |
| `ir_tx_pin` | `packages/esp360_remote_tx.yaml` | IR TX GPIO. |
| `rf_rx_pin` | `packages/esp360_remote_rx.yaml` | RF RX GPIO. |
| `ir_rx_pin` | `packages/esp360_remote_rx.yaml` | IR RX GPIO (commented example). |

## Secrets required
Define these in ESPHome `secrets.yaml` for the common networking pieces (secrets
are not stored in this repo):

| Secret | Used by | Purpose |
| --- | --- | --- |
| `wifi_ssid` | `packages/wifi.yaml` | WiFi SSID. |
| `wifi_password` | `packages/wifi.yaml` | WiFi password. |
| `ap_password` | `packages/wifi.yaml` | Fallback AP password. |
| `api_encryption_key` | `packages/api.yaml` | ESPHome API encryption key. |
| `ota_password` | `packages/ota.yaml` | OTA password. |

## Notes
- BLE proxy packages start scans when an API client connects and stop when all clients disconnect.
- Remote TX exposes API services for raw RF/IR transmission.

## Add a new board or package

Checklist:
- Create the YAML in `boards/` or `packages/`.
- Add required substitutions or secrets to the tables above.
- If it has unique defaults or constraints, document them in `boards/README.md` or this file.
- Add an example device config (optional but helpful).
- Verify it composes cleanly with `packages/identity.yaml` and `packages/api.yaml`.

## External docs
- ESPHome documentation: https://esphome.io/
- ESPHome packages: https://esphome.io/guides/configuration-types.html#packages
- ratgdo ESPHome config: https://github.com/ratgdo/esphome-ratgdo
- Everything Presence Lite: https://github.com/Everythingsmarthome/everything-presence-lite

## Contributing
See `CONTRIBUTING.md`.

## Changelog
See `CHANGELOG.md`.

## License
See `LICENSE`.
