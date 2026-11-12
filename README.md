# Firmware releases

Public firmware files for devices supported by the Marivo app. The app reads `manifest.json` from this repository (no sign-in) and downloads firmware from the Releases of this repository.

| Item | Location |
|---|---|
| Firmware index | `manifest.json` on `main` |
| Firmware files | Release assets, tag `<series>-v<version>-b<build>` |

`manifest.json` (schema 1):

| Field | Meaning |
|---|---|
| `series` | Product series, e.g. `sw-shallow-anchor` |
| `product` | Product code used by the OTA protocol |
| `target` | Bluetooth chip, e.g. `ch582` |
| `hardware` | Hardware version `major.minor`; firmware is only offered to the same hardware version |
| `version`, `build` | Firmware version and build number |
| `channel` | `stable` (all users) or `test` (engineering mode only) |
| `size`, `sha256` | Size in bytes and SHA-256 (lowercase hex) of the file |
| `url` | Download URL (release asset) |
| `published` | Release date |
| `notes` | Release notes by language code (`en`, `zh`, `ru`, `ja`, `pt`, `es`) |

Releases are created with the release script in the firmware source repository; do not edit entries by hand. Upload the release asset first, then push `manifest.json`.
