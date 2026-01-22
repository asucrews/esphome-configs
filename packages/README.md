# Packages

Reusable ESPHome fragments. These are intended to be composed together in
`devices/` or your own node configs.

## Usage
Include locally or via GitHub.

```yaml
packages:
  identity: ./packages/identity.yaml
  api: ./packages/api.yaml
  ota: ./packages/ota.yaml
  wifi: ./packages/wifi.yaml
```

```yaml
packages:
  identity: github://asucrews/esphome-configs/packages/identity.yaml@main
  api: github://asucrews/esphome-configs/packages/api.yaml@main
  ota: github://asucrews/esphome-configs/packages/ota.yaml@main
  wifi: github://asucrews/esphome-configs/packages/wifi.yaml@main
```

## Package catalog

Core:
- `packages/identity.yaml` - node identity.
- `packages/identity_dio.yaml` - identity with flash mode DIO.
- `packages/api.yaml` - encrypted ESPHome API.
- `packages/ota.yaml` - OTA password.
- `packages/wifi.yaml` - WiFi + captive portal.
- `packages/wifi_epl.yaml` - WiFi for Everything Presence Lite (no power save, AP SSID uses `friendly_name`).
- `packages/common.yaml` - uptime, WiFi signal, internal temp, restart buttons.
- `packages/time.yaml` - SNTP time sync.

Connectivity:
- `packages/ble.yaml` - BLE stack base.
- `packages/ble_proxy.yaml` - active BLE proxy with scan control.
- `packages/ble_tracker.yaml` - iBeacon config.
- `packages/api_ble_tracker.yaml` - API hooks to start/stop scans.

Sensors:
- `packages/i2c_bus_a.yaml` - I2C bus definition.
- `packages/sensors/bh1750_0x23.yaml` - BH1750 lux.
- `packages/sensors/shtcx_0x70.yaml` - SHTCx temperature/humidity with adjustable offsets.

Indicators:
- `packages/status_led.yaml` - status LED output/light.

Remotes:
- `packages/esp360_remote_tx.yaml` - RF/IR transmitter pins.
- `packages/esp360_remote_rx.yaml` - RF receiver (IR example commented).
- `packages/api_services/remote_tx.yaml` - API services to send RF/IR.
