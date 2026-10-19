# Changelog

## v1.7.23 — 2026-10-20

- **App builder support**: user apps now register through a simple list —
  one source file + one line — and appear in the Tools menu automatically
  (no menu/dispatch editing). Demo App included as the template; the MCP
  bridge can create, build, flash and run new apps end to end
- Console-injected taps are one-shot, so automated navigation is reliable

## v1.7.22 — 2026-10-20

- **Remote-test console** over USB serial: nav-bar taps can be injected and
  state/battery read back externally (single-letter commands), so the whole
  device can be driven and verified by automated tooling; deterministic
  single-step mode for tests

## v1.7.21 — 2026-10-20

- **Removed the jamming tools** (BLE Jammer, SubGHz Jammer) from the menus —
  CW interference transmitters cannot legally be sold or operated (FCC/CE)
  and were written for a 3-radio board this hardware does not have. The
  defensive **Jamming Detector** stays; the SDR Spectrum, Link Test, sniffer
  and scanner tools cover analysis and testing the right way

## v1.7.20 — 2026-10-20

- **Fix: SDR Spectrum hid the bottom buttons** — the signal log drew over
  the touch bar; the whole layout now fits above it (header / spectrum /
  waterfall / detected-signals log, all in view)

## v1.7.19 — 2026-10-20

- **SDR Spectrum rebuilt as a real analyzer**: amber peak-hold trace over
  the live spectrum, dBm scale and frequency axis, ×4/×16 zoom that follows
  signal activity, sweeps-per-second readout, and a **DETECTED SIGNALS log**
  — every burst recorded with frequency, strength and duration (and echoed
  to USB serial)

## v1.7.18 — 2026-10-20

- **Fix: SDR Spectrum now really sweeps** — a library quirk retuned the
  radio to its default frequency on every step, so the "sweep" measured one
  frequency and the display stayed flat. Each step now tunes explicitly
- SDR Spectrum checks for the CC1101 at open (says CC1101 NOT FOUND if the
  radio is absent) and Exit works during the sweep

## v1.7.17 — 2026-10-20

- **Touch-first input**: every tap on the on-screen nav bar is now latched,
  so quick taps always register no matter what the tool is doing — the
  screen is the device's only input and it now behaves like it

## v1.7.16 — 2026-10-19

- **New boot animation**: the Skull Rain screen — the skull melts down the
  display while green matrix rain falls and locks the second skull in
- **New GPS Guard** (More → GPS): live jamming/spoofing anomaly monitor —
  watches for signal loss after a healthy fix, impossible position jumps
  and time walking backwards
- **New Coordinates** (More → GPS): live position in decimal degrees,
  D-M-S, Maidenhead grid square and maps format
- The SubGHz spectrum tool is now labelled **SDR Spectrum** so it is easy
  to find (it was already there — SubGHz → SDR Spectrum)

## v1.7.15 — 2026-10-19

- All of v1.7.14 (RF Spectrum waterfall, TV Power, IR Repeater) **plus a
  fix**: tapping Replay Attack on the SubGHz menu had lost its startup
  lines in v1.7.14 — restored

## v1.7.14 — 2026-10-19

- New **RF Spectrum** (SubGHz → Spectrum): CC1101 swept spectrum analyzer
  with live peak readout and a scrolling waterfall across the 315/433/868/915
  ISM bands — the SDR-style view of everything talking around you
- New **TV Power** (More → IR Remote): power codes for Samsung, LG, Sony,
  Philips and Panasonic — fire one brand or ALL
- New **IR Repeater** (More → IR Remote): loops the last captured IR code
  every 2.5 s for receiver/range testing

## v1.7.13 — 2026-10-19

- Boot art fix: the Skull Jaw is now drawn with its **real ASCII characters
  at true proportions** (the previous scaled mask distorted it into a blob)
- The whole boot sequence is now **phosphor green** — art, chrome, wordmark
  and logo reveal

## v1.7.12 — 2026-10-19

- Boot mark replaced with the **ASCII Skull Jaw** art (the jaw-skull piece)
  — shown on every theme

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
