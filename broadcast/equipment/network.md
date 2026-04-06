# Network

**Device:** GL.iNet Beryl AX (GL-MT3000) travel router
**Purpose:** Dedicated internet gateway for all broadcast equipment

## Setup

1. **WAN input:** Connect event-provided or NSMT-provided internet to the router's WAN port. Prefer a wired ethernet connection over Wi-Fi repeater mode whenever possible.
2. **LAN output:** Connect the Mac to the router via ethernet-to-USB-C dongle (or native ethernet port if available). The Mac needs internet for RTMP streaming to Castr/YouTube.
3. **All internet traffic** routes through the NSMT travel router — this keeps broadcast traffic isolated from venue Wi-Fi congestion.

## Why a Travel Router

- Venues often have unreliable or congested Wi-Fi
- A dedicated router gives the broadcast team a controlled, consistent network
- Hardwired connection between router and Mac eliminates Wi-Fi variability for the stream
- The router can also provide Wi-Fi to other broadcast devices (iPad for stats, etc.) if needed

## Best Practices

- **Always prefer hardwired connections** — Wi-Fi should be a last resort for the streaming Mac
- Test upload speed before broadcast starts (minimum 10 Mbps recommended for 6000 kbps stream + headroom)
- If venue only offers Wi-Fi, configure the GL-MT3000 in repeater mode and still run ethernet from it to the Mac
- Keep the router powered via USB-C — it can run off a portable battery pack in a pinch

## Cross-References

- [Pre-Game Runbook](../runbooks/pre-game.md) — network setup steps during pre-game
- [Live Broadcast Runbook](../runbooks/live-broadcast.md) — monitoring network during show
- [Troubleshooting](../runbooks/troubleshooting.md) — stream dropping / disconnecting fixes
