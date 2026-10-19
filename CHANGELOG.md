# Changelog

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
