# Changelog

All notable changes to this repo are documented here.
Last updated: 2026-01-22

## Unreleased
### Added
- Code of Conduct.
- Security policy.
- Weekly GitHub Actions snapshot workflow (tags + releases).

### Changed
- Link Code of Conduct and Security policy from README and CONTRIBUTING.
- Add validation scope guidance to CONTRIBUTING.
- Add a security contact handle.
- Disable MAC suffix naming in identity packages.
- Adjust SHTCx 0x70 temperature offset calibration.
- Disable WiFi power save mode by default.
- Disable identity package reference in everything_presence_lite device config.

## 2026-01-22
### Added
- Expanded README coverage for boards, devices, and packages.
- Device template and contribution guidance.
- Changelog and contribution guide.

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
