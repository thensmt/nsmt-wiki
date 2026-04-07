---
title: "ADR-002: Firebase vs WebSocket"
type: decision
status: accepted
created: 2026-04-06
updated: 2026-04-06
tags:
  - architecture
  - firebase
  - websocket
  - transport
---

# ADR-002: Firebase vs WebSocket

**Date:** 2026-04-01
**Status:** accepted

## Context

Project Austin needs to support both local WebSocket mode (for direct Mac operation) and Firebase RTDB mode (for YoloBox/remote operation). These are two different real-time transports serving different deployment scenarios.

## Decision

Maintain both WebSocket-based (`nsmt_fox_overlay_ws.html`) and Firebase-based (`yolo-overlay.html`) overlay/control pairs. Firebase enables remote operation via YoloBox without requiring a local server running on-site.

## Consequences

- Two sets of overlay/control files to maintain (WebSocket and Firebase variants)
- Firebase adds a cloud dependency but enables portable, location-independent operation
- WebSocket remains the lower-latency option for local setups where the server and OBS run on the same machine
- Both transports share the same game state shape, so overlays are visually identical regardless of transport

## Cross-References

- [Project Austin](../projects/austin.md) — the project that implements both transport modes
- [Firebase](../systems/firebase.md) — cloud infrastructure for the Firebase transport
- [WebSocket Protocol](../systems/websocket-protocol.md) — local transport protocol
- [Video Transport](../broadcast/equipment/video-transport.md) — YoloBox hardware that drives the Firebase transport need
