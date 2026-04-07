---
title: Pre-Game Setup Runbook
type: runbook
status: active
created: 2026-04-06
updated: 2026-04-06
tags:
  - setup
  - checklist
  - broadcast
---

# Pre-Game Setup Runbook

Step-by-step checklist. Start **90 minutes before tip-off** minimum.

---

## 1. Equipment Setup

### Cameras
- [ ] Mount [Sony FX3](../equipment/cameras.md) on SmallRig AD-100 tripod at elevated position
- [ ] Assemble [SmallRig Classic 4480 shoulder rigs](../equipment/cameras.md) for baseline cameras
- [ ] Attach [Teradek Ace 750 TX](../equipment/video-transport.md) to each camera rig
- [ ] Install V-mount batteries on all camera rigs and Teradek units (see [Power](../equipment/power.md))

### Teradek Pairing
- [ ] Power on all Teradek TX units (on cameras)
- [ ] Power on all Teradek RX units (at production table)
- [ ] Verify TX/RX pairing — each camera feed should appear on corresponding RX output
- [ ] Connect RX HDMI outputs to [YoloBox Extreme](../equipment/video-transport.md) inputs

### Production Table
- [ ] Set up [YoloBox Extreme](../equipment/video-transport.md) — power on, insert UHS-II SD card
- [ ] Connect [Rodecaster Pro I](../equipment/audio.md) — insert micro SD for backup recording
- [ ] Connect YoloBox HDMI out to [Elgato 4K capture card](../equipment/video-transport.md)
- [ ] Connect Elgato USB-C to Mac
- [ ] Set up travel router and verify network connectivity

---

## 2. Software Setup

- [ ] Start scorebug server on Mac
- [ ] Open OBS — load correct scene collection
- [ ] Configure OBS scenes (verify NSMT Game, Pre-Game/Halftime, Starting Lineup, Post-Game)
- [ ] Open overlay page in Chrome (browser source URL)
- [ ] Open [control interface](../roles/stat-tracker.md) in Chrome
- [ ] Test WebSocket / Firebase connection between control and overlay
- [ ] Verify overlay appears correctly in OBS browser source (transparent background)

---

## 3. Audio Check

- [ ] Plug all headsets into [Rodecaster Pro I](../equipment/audio.md) channels
- [ ] Set input levels for each announcer mic — speak at broadcast volume
- [ ] Confirm Rodecaster output is reaching YoloBox
- [ ] Verify audio passes through Elgato to OBS (check [EDID settings](troubleshooting.md) if no audio)
- [ ] Set macOS audio sample rate to 48kHz
- [ ] Configure OBS audio: Monitor and Output in Advanced Audio Properties
- [ ] Test OBS audio filters chain: Compressor, Noise Gate, Limiter (in order)

---

## 4. Video Check

- [ ] Verify all camera feeds visible in YoloBox input selector
- [ ] Check each camera's framing and focus
- [ ] Verify Elgato capture appears in OBS as video source
- [ ] Confirm overlay transparency is correct (no black background)
- [ ] Test scene switching with [OBS hotkeys](../roles/tech-director.md): F1, F2, F3, F4
- [ ] Verify Studio Mode is active (preview + program)

---

## 5. Comms Check

- [ ] Power on all [Hollyland Solidcom SE](../equipment/comms.md) headsets
- [ ] Verify all headsets are connected to hub (check LED indicators)
- [ ] Do full comms check: TD calls each camera op by name, each confirms
- [ ] Check battery levels on all headsets — **do not start broadcast with low batteries** (see [Hoopfest lesson](../events/hoopfest-2026-03-22.md))

---

## 6. Stream Test

- [ ] Verify RTMP stream key is configured in OBS (Castr or direct platform)
- [ ] Start a 30-second test stream
- [ ] Check stream on receiving end (phone or second device)
- [ ] Verify audio/video sync
- [ ] Stop test stream
- [ ] Confirm OBS recording path is set (MKV format to ~/Movies/NSMT Broadcasts/)
- [ ] Keep backup YouTube stream key ready in case of Castr issues

---

## Final Check

- [ ] All crew in position with working comms
- [ ] Score bug showing correct teams, 0-0 score, correct quarter
- [ ] OBS on NSMT Game scene (F1), Studio Mode active
- [ ] Recording started (Ctrl+Shift+R)

**Go live.**

## Cross-References
- [Tech Director](../roles/tech-director.md) — leads the pre-game setup
- [Camera Operator](../roles/camera-operator.md) — camera-specific setup
- [Stat Tracker](../roles/stat-tracker.md) — scorebug software setup
- [Announcer](../roles/announcer.md) — audio check
- [Troubleshooting](troubleshooting.md) — if anything fails during setup
