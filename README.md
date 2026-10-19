# SHARKDIV — Firmware Updates

Official firmware releases for the **SHARKDIV** wireless multi-tool
(ESP32-S3, 16 MB flash, 2.4" ILI9341 touchscreen).

> **SHARKDIV hardware only.** This firmware is built for the SHARKDIV board
> (ESP32-S3 / 16 MB). It will not work correctly on other boards.

## Latest release

**v1.7.23** — see [Releases](https://github.com/M5Shark/SHARKDIV-updates/releases)
to download.

| File | Use when |
|---|---|
| `SHARKDIV-firmware-vX.Y.Z-full-16MB.bin` | Flashing with USB + esptool (one file, includes bootloader + partition table + app). **Recommended.** |
| `SHARKDIV-ota-vX.Y.Z-app-only.bin` | Updating from the device's own web updater (**Settings → Firmware Update**) or any OTA tool. Smaller download. |

## Flashing over USB (full image)

1. Install `esptool` (`pip install esptool`) and plug SHARKDIV in by USB.
2. If the port doesn't appear: hold **BOOT**, tap **RESET**, release **BOOT**.
3. Flash the **full** image — replace PORT with your device
   (`/dev/cu.usbserial-…` on macOS, `/dev/ttyUSB0`/`COM5` elsewhere):

```bash
esptool.py --chip esp32s3 --port PORT --baud 115200 \
  write_flash 0x0 SHARKDIV-firmware-v1.7.23-full-16MB.bin
```

Use **115200** baud — the USB bridge is not stable at higher speeds.
Your saved settings (theme, calibration) are kept.

## Responsible use

SHARKDIV is a security-research and education tool. Use it only on networks
and devices you own or are explicitly authorised to test, and only where
local law allows. You are responsible for how you use it.

## Credits

Firmware is based on the open-source
[ESP32-DIV](https://github.com/cifertech/ESP32-DIV) by **CiferTech** (MIT) —
see [LICENSE](LICENSE). SHARKDIV build, theme, and additional tooling by M5Shark.
