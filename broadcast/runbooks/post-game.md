# Post-Game Runbook

---

## Immediate (While Still Live)

1. Capture final score in scorebug — [Stat Tracker](../roles/stat-tracker.md) confirms
2. Switch to Post-Game scene (**F4**) for interviews if applicable
3. [Sideline Reporter](../roles/announcer.md) conducts post-game interviews (if available)
4. [Announcers](../roles/announcer.md) wrap up commentary

---

## End Stream

1. Stop stream in OBS (Settings > Stream > Stop Streaming, or toolbar button)
2. Stop recording (**Ctrl+Shift+R**)
3. Remux recording: **File > Remux Recordings** — convert MKV to MP4
4. Save to `~/Movies/NSMT Broadcasts/` with naming convention: `YYYY-MM-DD_Event-Name.mp4`

---

## Equipment Teardown

- [ ] Power off all [Teradek TX/RX](../equipment/video-transport.md) units
- [ ] Remove V-mount batteries from all rigs — begin charging
- [ ] Power off [YoloBox Extreme](../equipment/video-transport.md) — remove SD card, label it
- [ ] Power off [Rodecaster Pro I](../equipment/audio.md) — remove micro SD backup, label it
- [ ] Disconnect [Elgato 4K](../equipment/video-transport.md) from Mac
- [ ] Power off [Hollyland Solidcom SE](../equipment/comms.md) headsets — begin charging immediately
- [ ] Break down camera rigs, tripod, shoulder rigs
- [ ] Coil and pack all HDMI and USB-C cables
- [ ] Pack travel router

---

## Data Management

- [ ] Verify MP4 recording is playable and complete
- [ ] Back up Rodecaster micro SD recording
- [ ] Back up YoloBox SD card (program + ISO recordings)
- [ ] Export final stats from scorebug system

---

## Debrief Notes

After every broadcast, document:
- What went well
- What went wrong
- Equipment issues encountered
- Action items for next event

File as an event report in [broadcast/events/](../events/) — see the [Hoopfest report](../events/hoopfest-2026-03-22.md) as a template.

## Cross-References
- [Tech Director](../roles/tech-director.md) — leads post-game procedures
- [Stat Tracker](../roles/stat-tracker.md) — final score capture
- [Announcer](../roles/announcer.md) — post-game interviews
- [Power](../equipment/power.md) — battery charging
- [Pre-Game Runbook](pre-game.md) — reverse of setup
