# Changelog

## v1.7.4 — 2026-10-19

- Battery indicator fix: reads the IP5306 fuel gauge over the full range
  (intermediate charge levels no longer show 0%), keeps the last good value
  if a read glitches
- New ctOS-style skin, boot animation and menus (M5SHARK look), 4 themes
- New tools: WiFi Radar, SSID Rotator, BLE Spam (SwiftPair / Samsung / Google)

## v1.7.3 — 2026-10-19

- nRF24 (2.4 GHz) tools reworked: sniffer/replay/MouseJack now use promiscuous
  mode and show the real over-the-air address of captured devices
- ESB Sniffer: full 125-channel band coverage, alternates 2/1 Mbps, batched
  SD logging (far fewer missed packets)
- ESB Replay: replays to the actually captured address/channel
- 2.4 GHz Scanner: true 125-channel sweep, working noise-floor calibration,
  ~2x faster screen refresh
- Stability and build fixes (links on stock Arduino-ESP32 2.0.10, removed dead
  Classic-BT scan path)

## v1.7.2

- Previous public build (Hacker Edition base).
