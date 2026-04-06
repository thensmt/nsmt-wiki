# Live Broadcast Runbook

Procedures for during the broadcast. The [Tech Director](../roles/tech-director.md) leads all of these.

---

## Scene Switching Protocol

OBS runs in **Studio Mode** — left panel is preview, right panel is program (live).

| Key | Scene |
|---|---|
| **F1** | NSMT Game (main broadcast) |
| **F2** | Pre-Game / Halftime |
| **F3** | Starting Lineup |
| **F4** | Post-Game |

Always preview the next scene before cutting live. Never blind-cut.

---

## Score Updates Flow

1. Play happens on court
2. [Stat Tracker](../roles/stat-tracker.md) enters update in control interface
3. Overlay auto-updates via WebSocket / Firebase RTDB
4. Score bug reflects new score on broadcast immediately

No action needed from TD — the overlay updates are automatic.

---

## Instant Replay Workflow

1. TD sees a big play
2. Press **Ctrl+Shift+S** to save the replay
3. Replay plays in the scene automatically
4. Replay auto-hides when complete
5. Resume normal camera coverage

---

## Commercial Break Procedure

1. TD announces "going to break" on [intercom](../equipment/comms.md)
2. Switch to break scene or graphic
3. Mute broadcast audio if needed
4. Camera ops can reposition, check batteries
5. TD counts down return: "Back in 30... 15... 10... 5, 4, 3, 2, 1"
6. Cut back to NSMT Game scene (F1)
7. [Announcers](../roles/announcer.md) pick up narration

---

## Halftime Transition

1. Switch to Pre-Game/Halftime scene (**F2**)
2. See [Halftime Runbook](halftime.md) for full procedure

---

## Stream Health Monitoring

Monitor the **OBS Stats dock** throughout the broadcast:

- **Dropped frames:** Should be 0%. If climbing, check network via travel router.
- **Encoding lag:** Should be near 0. If high, reduce output resolution or bitrate.
- **CPU usage:** Keep below 80%.

### Backup Plan
- Keep a backup YouTube stream key ready
- If Castr has issues, switch RTMP destination in OBS Settings > Stream
- Brief interruption is acceptable — get back online fast

---

## Emergency Procedures

- **Camera feed lost:** TD switches to another camera while [camera op](../roles/camera-operator.md) troubleshoots. Check [Teradek](../equipment/video-transport.md) pairing, HDMI, battery.
- **Audio lost:** Check [Elgato EDID](troubleshooting.md), Rodecaster connection, OBS audio device.
- **Overlay frozen:** [Stat Tracker](../roles/stat-tracker.md) refreshes browser source in OBS, checks server.
- **Stream drops:** Check network, verify RTMP key, check OBS Stats. Switch to backup stream key if needed.
- **Intercom failure:** Use hand signals or phone as backup for TD-to-camera-op communication.

## Cross-References
- [Tech Director](../roles/tech-director.md) — runs all of these procedures
- [Stat Tracker](../roles/stat-tracker.md) — score update flow
- [Announcer](../roles/announcer.md) — commercial break coordination
- [Camera Operator](../roles/camera-operator.md) — takes direction from TD
- [Halftime Runbook](halftime.md) — halftime-specific procedures
- [Troubleshooting](troubleshooting.md) — detailed fixes for common issues
