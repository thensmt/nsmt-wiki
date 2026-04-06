# OBS Configuration

OBS runs on the same Mac as the scorebug server. **Always use Studio Mode.**

## Scenes

### 1. NSMT Game (main)
- Browser Source overlay (`localhost:8000/nsmt_fox_overlay_ws.html`, 1920x1080, transparent)
- Elgato 4K video capture
- Black background

### 2. Pre-Game / Halftime
- NSMT branded slate image
- Black background

### 3. Starting Lineup / Full Screen Graphic
- Browser source for lineup/stats display
- Black background

### 4. Post-Game
- Lower third overlay
- Elgato feed

## Browser Source Settings

| Setting | Value |
|---------|-------|
| URL | `localhost:8000/nsmt_fox_overlay_ws.html` |
| Resolution | 1920x1080 |
| Custom CSS | `body { background: transparent !important; }` |
| FPS | 30 |
| Shutdown when not visible | **OFF** |
| Refresh on scene active | **OFF** |

## Elgato 4K Settings

- Resolution: 1920x1080
- Custom audio device selected
- Deinterlacing: off

## Audio Fix Checklist

1. Elgato Capture Device Utility: set EDID to **Internal/Merged** (NOT Display)
2. OBS: select custom audio device for Elgato source
3. macOS: set audio sample rate to **48kHz**
4. OBS Advanced Audio: set to **Monitor and Output**
5. Mute the Browser Source audio

## Audio Filters (on Elgato, in order)

1. Compressor
2. Noise Gate
3. Limiter

## Instant Replay

- Replay Buffer: 30 seconds
- Auto-start with streaming
- Save hotkey: `Ctrl+Shift+S`
- Script: `instant-replay.lua`
- Media Source: "Instant Replay" (hidden by default, shown on save)

## Output Settings

### Streaming
- Rate control: CBR 4500-6000 kbps
- Encoder: H264 hardware
- Keyframe interval: 2 seconds
- Profile: High

### Recording
- Format: MKV (remux to MP4 after broadcast)
- Save path: `~/Movies/NSMT Broadcasts/`

## Hotkeys

| Key | Action |
|-----|--------|
| F1 | NSMT Game |
| F2 | Pre-Game / Halftime |
| F3 | Starting Lineup |
| F4 | Post-Game |
| Ctrl+Shift+S | Save Replay |
| Ctrl+Shift+R | Start/Stop Recording |

## Cross-References

- [Live Broadcast Runbook](../broadcast/runbooks/live-broadcast.md) — step-by-step broadcast procedure
- [Tech Director Role](../broadcast/roles/tech-director.md) — who operates OBS
- [Video Transport Equipment](../broadcast/equipment/video-transport.md) — Elgato and signal chain
- [Troubleshooting](../broadcast/runbooks/troubleshooting.md) — Common OBS and stream issues
- [Project Austin](../projects/austin.md) — Standalone operator package that uses these OBS settings
