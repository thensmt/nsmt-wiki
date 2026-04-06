# Troubleshooting

Common issues and fixes for NSMT broadcasts. Organized by symptom.

---

## Elgato No-Audio

The most common issue. The [Elgato 4K capture card](../equipment/video-transport.md) frequently fails to pass audio from YoloBox to Mac.

**Fix:**
1. Open Elgato software — set EDID to **Internal/Merged** (not Display)
2. In OBS, set a **custom audio device** for the Elgato source (not "Use device default")
3. In macOS System Settings > Sound, verify sample rate is **48kHz**
4. In OBS, right-click the Elgato audio source > **Advanced Audio Properties** > set to **Monitor and Output**

If audio still missing after all four steps, unplug and re-plug the Elgato USB-C cable.

---

## Camera Feed Not Showing in YoloBox

**Symptoms:** One or more camera inputs show black/no signal in [YoloBox Extreme](../equipment/video-transport.md).

**Fix:**
1. Check [Teradek TX/RX](../equipment/video-transport.md) pairing — LED indicators should show linked
2. Check HDMI cable from Teradek RX to YoloBox — reseat both ends
3. Verify YoloBox input selection matches the physical HDMI port
4. Check [V-mount battery](../equipment/power.md) on both TX and RX
5. Power cycle the Teradek TX/RX pair

---

## Scorebug Overlay Not Updating

**Symptoms:** Score or stats on overlay are stale, not reflecting changes made in control interface.

**Fix:**
1. Check WebSocket connection status in the control interface (should show "Connected")
2. If disconnected, refresh the control page in Chrome
3. In OBS, right-click the browser source > **Refresh**
4. Verify the scorebug server is running on the Mac (`node server.js` or check process)
5. If using Firebase: check Firebase RTDB console for live data updates

See also: [Stat Tracker](../roles/stat-tracker.md) for control interface details.

---

## Hollyland Intercom Dropouts

**Symptoms:** [Intercom](../equipment/comms.md) audio cuts in and out, or headset disconnects entirely.

**Fix:**
1. **Check battery level first** — this was the cause at [Hoopfest](../events/hoopfest-2026-03-22.md)
2. Check range — 1,100 ft max, but walls and interference reduce this
3. Check 2.4 GHz interference — other Wi-Fi networks, travel router, Bluetooth devices can cause issues
4. Move the Hollyland hub unit to a higher/clearer position
5. Power cycle the affected headset

---

## Audio Clipping / Distortion

**Symptoms:** Broadcast audio is distorted, peaking, or has audible clipping.

**Fix:**
Check the OBS audio filters chain. They must be in this order:
1. **Compressor** — reduces dynamic range
2. **Noise Gate** — cuts background noise during silence
3. **Limiter** — hard ceiling to prevent clipping

Also check:
- [Rodecaster Pro I](../equipment/audio.md) input levels — reduce gain on the clipping channel
- OBS audio mixer levels — keep peaks in yellow, never red

---

## Stream Dropping / Disconnecting

**Symptoms:** Stream goes offline, viewers see buffering or "stream ended."

**Fix:**
1. Check network connectivity via travel router
2. Open **OBS Stats dock** — check "Dropped Frames" percentage
3. If frames are dropping: reduce output bitrate in OBS Settings > Output
4. Verify RTMP stream key is correct and hasn't expired
5. If Castr is having issues, switch to backup YouTube stream key:
   - OBS Settings > Stream > change Server/Stream Key
   - Brief interruption is acceptable — get back online fast
6. Check Mac CPU/GPU usage — close unnecessary applications

---

## OBS Scenes / Sources Missing

**Symptoms:** Scenes are empty or sources show "not found."

**Fix:**
1. Verify correct scene collection is loaded (Scene Collection menu)
2. For browser sources: check that the scorebug server is running and the URL is correct
3. For video capture: check that Elgato is connected and recognized by macOS
4. Reimport scene collection from backup if needed

## Cross-References
- [Video Transport](../equipment/video-transport.md) — Elgato, Teradek, YoloBox details
- [Audio](../equipment/audio.md) — Rodecaster, headset setup
- [Comms](../equipment/comms.md) — Hollyland intercom
- [Power](../equipment/power.md) — battery issues
- [Tech Director](../roles/tech-director.md) — who handles most troubleshooting
- [OBS Configuration](../../systems/obs-configuration.md) — scene layout, hotkeys, output settings
- [Live Broadcast Runbook](live-broadcast.md) — emergency procedures during show
