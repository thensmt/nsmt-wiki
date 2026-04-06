# Video Transport

## Signal Flow

```
Baseline Cams (+ Teradek TX) ──wireless──▶ Teradek RX ──HDMI──▶ YoloBox Extreme
Top Camera   (+ Teradek TX) ──wireless──▶ Teradek RX ──HDMI──▶ YoloBox Extreme
Mics/Headsets ──────────────────────────▶ Rodecaster Pro I ───▶ YoloBox Extreme

YoloBox Extreme ──HDMI out──▶ Elgato 4K ──USB-C──▶ Mac (OBS)

OBS composites video + browser source overlay ──▶ RTMP stream + local MKV recording
```

---

## Teradek Ace 750

**Model:** Teradek Ace 750
**Qty:** TX on each camera, RX at production table
**Used by:** [Camera Operators](../roles/camera-operator.md), [Tech Director](../roles/tech-director.md)

### Specs
- Wireless HDMI video transmitter/receiver system
- TX mounted on each camera rig
- RX units at production table, HDMI out to YoloBox Extreme

### Power
- **Transmitters (TX):** powered by V-mount batteries on camera rigs
- **Receivers (RX):** powered by V-mount batteries at production table
- See [Power](power.md) for battery details

---

## YoloBox Extreme

**Model:** YoloLiv YoloBox Extreme
**Qty:** 1
**Used by:** [Tech Director](../roles/tech-director.md)

### Specs
- Multi-camera switcher and encoder
- Receives camera feeds via HDMI in from Teradek RX units
- HDMI out to Elgato 4K capture card

### Configuration
- Inputs: HDMI from each Teradek RX (one per camera)
- Output: HDMI program feed to Elgato 4K
- **UHS-II SD card required** for program recording + ISO recording
- Audio input from [Rodecaster Pro I](audio.md) via USB-C or analog

---

## Elgato 4K Capture Card

**Model:** Elgato 4K60 Pro (or similar)
**Qty:** 1
**Used by:** [Tech Director](../roles/tech-director.md)

### Specs
- HDMI input from YoloBox Extreme
- USB-C output to Mac
- Carries both audio and video in one cable

### Known Issues
- **No-audio problem:** EDID settings must be set to Internal/Merged (not Display). Custom audio device in OBS, 48kHz sample rate in macOS, Monitor and Output in Advanced Audio Properties. See [Troubleshooting](../runbooks/troubleshooting.md).

## Cross-References
- [Cameras](cameras.md) — source feeds
- [Audio](audio.md) — audio path into YoloBox
- [Power](power.md) — V-mount batteries for Teradek TX/RX
- [Tech Director](../roles/tech-director.md) — operates YoloBox and monitors signal chain
- [Pre-Game Runbook](../runbooks/pre-game.md) — Teradek pairing, video check
- [Troubleshooting](../runbooks/troubleshooting.md) — Elgato no-audio, camera feed issues
