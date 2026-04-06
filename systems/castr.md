# Castr

**Service:** [Castr](https://castr.com) — RTMP multistreaming
**Used by:** NSMT live broadcasts

## What It Does

Castr is the RTMP streaming service used for NSMT events. It receives a single RTMP stream from OBS and multistreams it to YouTube and other platforms simultaneously. This eliminates the need to configure multiple output destinations in OBS directly.

## How It Works

1. OBS streams to a Castr RTMP ingest URL with the event's stream key
2. Castr rebroadcasts to all configured destinations (YouTube, etc.)
3. The Tech Director monitors stream health in OBS and on the Castr dashboard

## Backup Plan

If Castr experiences issues during a broadcast, switch to the backup YouTube stream key directly:
- OBS Settings > Stream > change Server and Stream Key to YouTube's direct RTMP ingest
- Brief interruption is acceptable — priority is getting back online fast
- See [Troubleshooting](../broadcast/runbooks/troubleshooting.md) for the full stream-drop procedure

## Cross-References

- [Tech Director](../broadcast/roles/tech-director.md) — manages stream output and Castr during broadcasts
- [Pre-Game Runbook](../broadcast/runbooks/pre-game.md) — stream key configuration during setup
- [Live Broadcast Runbook](../broadcast/runbooks/live-broadcast.md) — monitoring stream health
- [Troubleshooting](../broadcast/runbooks/troubleshooting.md) — stream dropping / disconnecting fixes
