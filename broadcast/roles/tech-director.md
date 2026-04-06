# Tech Director

**Required for minimum crew:** Yes
**Equipment:** [YoloBox Extreme](../equipment/video-transport.md), [intercom headset](../equipment/comms.md), monitor
**Can double as:** Audio Engineer (if [Rodecaster](../equipment/audio.md) levels are set pre-game)

## Responsibilities
- Calls camera switches via [intercom](../equipment/comms.md)
- Cues graphics (scorebug, lower thirds)
- Manages commercial breaks
- Controls overall show flow
- Monitors stream health in OBS

## Setup Checklist
1. Power on [YoloBox Extreme](../equipment/video-transport.md) and verify all camera inputs
2. Connect [Rodecaster Pro I](../equipment/audio.md) audio feed to YoloBox
3. Verify [Elgato 4K](../equipment/video-transport.md) capture is showing in OBS
4. Open OBS, load correct scene collection
5. Verify overlay browser source is connected (WebSocket)
6. Put on [Hollyland intercom](../equipment/comms.md) headset, do comms check with all camera ops
7. Test all OBS hotkeys (see below)

## During Broadcast

### OBS Hotkeys

| Key | Action |
|---|---|
| **F1** | NSMT Game scene (main broadcast) |
| **F2** | Pre-Game / Halftime scene |
| **F3** | Starting Lineup scene |
| **F4** | Post-Game scene |
| **Ctrl+Shift+S** | Save instant replay |
| **Ctrl+Shift+R** | Start / stop recording |

### Studio Mode
- Uses Studio Mode to preview next scene before cutting live
- Left panel = preview, right panel = program (live)
- Transition with "Cut" or custom transition button

### Instant Replay Workflow
1. See a big play
2. Hit **Ctrl+Shift+S** to save replay
3. Replay plays automatically in scene
4. Auto-hides when complete

### Stream Health
- Monitor OBS Stats dock throughout broadcast
- Watch for dropped frames and encoding lag
- Keep backup stream key ready (YouTube fallback if [Castr](../../sources/) has issues)

## Common Issues
- If camera feed disappears from YoloBox, check [Teradek pairing](../equipment/video-transport.md) and HDMI cables
- If overlay stops updating, check WebSocket — see [Troubleshooting](../runbooks/troubleshooting.md)
- If audio is missing from stream, check [Elgato EDID settings](../runbooks/troubleshooting.md)

## Cross-References
- [Video Transport](../equipment/video-transport.md) — YoloBox, Elgato, signal chain
- [Audio](../equipment/audio.md) — Rodecaster levels
- [Comms](../equipment/comms.md) — intercom for calling shots
- [Camera Operator](camera-operator.md) — takes direction from TD
- [Live Broadcast Runbook](../runbooks/live-broadcast.md) — full during-show procedures
- [Pre-Game Runbook](../runbooks/pre-game.md) — setup steps
