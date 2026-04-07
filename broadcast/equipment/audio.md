---
title: Audio
type: equipment
status: active
created: 2026-04-06
updated: 2026-04-06
tags:
  - audio
  - rodecaster
  - headsets
  - monitoring
---

# Audio

## Mixer — Rodecaster Pro I

**Model:** Rodecaster Pro I
**Qty:** 1
**Used by:** [Tech Director](../roles/tech-director.md), [Announcers](../roles/announcer.md)

### Specs
- Multi-channel podcast/broadcast mixer
- Audio out to [YoloBox Extreme](video-transport.md) via USB-C or analog
- Micro SD card slot for backup recording — **always insert a card before broadcast**

### Configuration
- Set levels pre-game during audio check
- Route mixed output to YoloBox Extreme
- Backup recording runs on micro SD simultaneously

---

## Headsets

| Headset | Qty | Assigned To | Role |
|---|---|---|---|
| Audio-Technica broadcast headset | 2 | Nels (play-by-play), Dwight (color) | [Announcer](../roles/announcer.md) |
| Sennheiser broadcast headset | 1 | Guest / sideline reporter | [Announcer](../roles/announcer.md) |

---

## Audio Monitoring

Audio must be monitored at three points in the signal chain:

1. **Rodecaster Pro I** — source levels from microphones
2. **YoloBox Extreme** — mixed audio entering the switcher
3. **Mac (OBS)** — final program audio going to stream

If any point shows clipping or silence, troubleshoot that segment of the chain. See [Troubleshooting](../runbooks/troubleshooting.md) for audio issues.

---

## Talkback System

**Status:** TBD

A talkback solution is needed for the TD/producers to cue on-air broadcasters (e.g., "coming back from break in 10 seconds"). This is separate from the [Hollyland Solidcom SE intercom](comms.md), which is used for production crew communication.

Options under evaluation — could be IFB earpieces, a second Hollyland channel, or a software solution.

## Known Issues
- No talkback system in place yet — announcers have no way to receive cues from TD during broadcast
- Rodecaster micro SD must be inserted manually before each event

## Cross-References
- [Announcer](../roles/announcer.md) — who uses the headsets
- [Tech Director](../roles/tech-director.md) — can double as audio engineer
- [Video Transport](video-transport.md) — audio flows into YoloBox with video
- [Pre-Game Runbook](../runbooks/pre-game.md) — audio check procedure
- [Troubleshooting](../runbooks/troubleshooting.md) — Elgato no-audio fix, clipping fixes
