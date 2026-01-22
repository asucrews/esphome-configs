# Changelog

All notable changes to this repo are documented here.

## Unreleased
### Added
- Expanded README coverage for boards, devices, and packages.
- Device template and contribution guidance.

### Changed
- Document that secrets live in ESPHome `secrets.yaml` (not this repo).

## 2026-01-21
### Added
- Core packages: identity, api, ota, wifi, time, common.
- Board presets for ESP32 DevKit, ESP32-C3-DevKitC-1, ESP32-C6-DevKitC-1.
- Device configs for Everything Presence Lite, ratgdo v2.5i, ESP360 remote, BLE trackers.
- BLE stack packages (base, proxy, tracker, API scan control).
- Sensor packages for BH1750 and SHTCx with I2C bus setup.
- RF/IR remote TX/RX packages and API services.
- Status LED package.

### Changed
- Standardize package naming and GitHub package references.
- Tune board configs and flash mode options.
- Update WiFi defaults and add fallback AP.
- Refine esp360_remote package composition.

### Fixed
- Typos, filename corrections, and substitution fixes across packages and devices.
