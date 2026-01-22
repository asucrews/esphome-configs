# Contributing

Thanks for contributing. Keep changes small and composable so devices stay easy
to reuse and share.

## Guidelines
- Prefer reusable `packages/` over per-device logic.
- Keep device files minimal and focused on wiring packages together.
- Use consistent names for substitutions (see `README.md`).
- Document new packages/boards in their respective README.
- Avoid committing secrets; keep them in ESPHome `secrets.yaml`.

## Validation scope
- For any change to `packages/`, `boards/`, or `devices/`, run
  `esphome config <device.yaml>` for at least one affected device.
- If you change substitutions or secrets, update `README.md` tables.

## Adding a package
1. Create the YAML in `packages/`.
2. Add any required substitutions or secrets to `README.md`.
3. If it depends on a board or feature, note that in `packages/README.md`.
4. Run `esphome config <device.yaml>` with a device that includes the package.

## Adding a board
1. Create the YAML in `boards/`.
2. Document it in `boards/README.md`.
3. Validate with `esphome config <device.yaml>`.

## Adding a device
1. Copy `devices/template.yaml` and fill in substitutions.
2. Reference shared packages whenever possible.
3. Add the device to `devices/README.md`.

## Code of Conduct
See `CODE_OF_CONDUCT.md`.

## Security
See `SECURITY.md` for responsible disclosure.
