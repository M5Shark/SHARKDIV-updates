# Changelog

## v1.7.11 — 2026-10-19

- **Fix: WiFi Radar and SSID Rotator did not open from a screen tap** —
  their touch-dispatch entries were missing (physical-button path only);
  every one of the 35 features now opens from both paths

## v1.7.10 — 2026-10-19

- **Fix: WiFi Radar** showed no APs — a leftover background scan made every
  scan return -1; the radio is now taken over cleanly and failed scans retry
- **Fix: SSID Rotator** hotspot often never started — now forces AP mode
  explicitly and reports AP FAILED instead of pretending to be on air

## v1.7.9 — 2026-10-19

- **Fix: tools that could trap you inside (Flock Hunter, RFID, GPS, ...)**
  — every tool now gets a touch bar with a working **Exit**, and quick taps
  register reliably (350 ms latch) instead of being missed by slow loops
- Boot mark now follows the theme like M5SHARK: Dark/Shark = ctOS skull,
  Hacker = horned demon, Light = grey alien

## v1.7.8 — 2026-10-19

- **Fix: device rebooted when opening WiFi or Bluetooth page 2** — the
  page-2 icon lists were shorter than their menus, so the renderer drew a
  null icon. All icon slots filled and icon drawing is now null-guarded

## v1.7.7 — 2026-10-19

- Boot splash now finishes with the **M5SHARK shark logo**: scan-bar wipe
  reveal, bright pulse, then the SHARKDIV brand block with version
- Full boot sequence: ctOS carrier-noise decode -> skull lock -> logo reveal

## v1.7.6 — 2026-10-19

- New **QR Code** (Tools): render scannable QR codes on screen — presets for
  the shop and update page, or type any text over USB serial (live preview)
- New **Channel Analyzer** (Tools): per-channel 2.4 GHz airtime meter — see
  which WiFi channels are crowded before you deploy, shortest bar = clearest

## v1.7.5 — 2026-10-19

- New **BLE Link Test** (Bluetooth page 2): pick a nearby BLE device and
  watch its live link quality — packet delivery vs expected rate, RSSI
  min/avg/max, worst dropout. Range-test your own trackers and headphones
- New **RF Source Finder** (2.4 GHz menu): passive energy meter that ranks
  the loudest 2.4 GHz channels and guides you toward the source with an
  A/B spot compare
- New games in Tools: **Snake** (nav pad steers) and **Reaction Test**
- Fix: "BLE Spam" now launches from touch tap (was button-only)

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
