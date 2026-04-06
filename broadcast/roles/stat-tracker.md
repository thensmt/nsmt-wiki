# Stat Tracker

**Required for minimum crew:** Yes
**Equipment:** Laptop or iPad running scorebug system, stat sheet
**Can double as:** Graphics operator (already controls on-screen stats)

## Responsibilities
- Enters live stats as plays happen
- Triggers score bug updates on the broadcast overlay
- Manages on-screen graphics (score, fouls, quarter, game clock)
- Runs the scorebug control interface

## Setup Checklist
1. Open scorebug control interface in Chrome:
   - Firebase/YoloBox system: `yolo-control.html`
   - WebSocket system: `nsmt_fox_control_ws.html`
2. Verify connection to overlay (WebSocket or Firebase RTDB)
3. Confirm overlay is visible in OBS browser source
4. Prepare stat sheet / roster with player numbers and names
5. Test a score update — verify it appears on the broadcast overlay

## During Broadcast
- Update score immediately after each basket
- Track fouls, timeouts, quarter changes
- Coordinate with [TD](tech-director.md) on any graphics cues
- Keep paper stat sheet as backup

## Common Issues
- **Overlay not updating:** Check WebSocket connection or Firebase RTDB link. Refresh browser source in OBS if needed. See [Troubleshooting](../runbooks/troubleshooting.md).
- **Control page disconnected:** Refresh the control page in Chrome. Verify the scorebug server is running on the Mac.
- **Wrong score displayed:** Double-check with official scorekeeper, correct in control interface

## Cross-References
- [Tech Director](tech-director.md) — coordinates graphics cues
- [Troubleshooting](../runbooks/troubleshooting.md) — overlay connection issues
- [Pre-Game Runbook](../runbooks/pre-game.md) — software setup steps
- [Live Broadcast Runbook](../runbooks/live-broadcast.md) — score update flow
- [Firebase](../../systems/firebase.md) — RTDB backing the YoloBox/cloud control interface
- [Project Austin](../../projects/austin.md) — the scorebug system the stat tracker operates
