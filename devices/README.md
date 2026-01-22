# Devices

Device configs assemble shared packages into complete ESPHome nodes. These files
are meant to be small and focused, with most behavior pulled from `packages/`
and `boards/`.

## Usage
Use these as starting points or reference configs. They already use GitHub
package references, so they work from another repo without copying files.

```yaml
packages:
  identity: github://asucrews/esphome-configs/packages/identity.yaml@main
  board: github://asucrews/esphome-configs/boards/idf/esp32dev.yaml@main
  api: github://asucrews/esphome-configs/packages/api.yaml@main
```

## Device list

| File | Purpose | Notes |
| --- | --- | --- |
| `devices/template.yaml` | Starter template | Copy and edit for new devices. |
| `devices/ratgdo-v25i.yaml` | Garage opener (ratgdo v2.5i) | Uses upstream ratgdo config. |
| `devices/everything_presence_lite.yaml` | Room presence sensor | Uses upstream EPL config + `wifi_epl`. |
| `devices/esp360_remote.yaml` | RF/IR hub | Includes RX/TX packages and API services. |
| `devices/ble_tracker_c3.yaml` | BLE tracker | ESP32-C3 board with proxy + tracker. |
| `devices/ble_tracker_c6.yaml` | BLE tracker | ESP32-C6 board with proxy + tracker. |
