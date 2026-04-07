---
title: Project Austin
type: project
status: active
created: 2026-04-06
updated: 2026-04-06
tags:
  - firebase
  - websocket
  - operator-package
  - cloud-functions
---

# Project Austin

**Repo:** `thensmt/scorebug`
**Location:** `~/Desktop/Livestream/scorebugfinal/`
**Stack:** HTML/CSS/JS, Firebase RTDB, Firebase Cloud Functions, WebSocket, Node.js
**Status:** Active — Firebase deploy completed 2026-04-06, 6 Cloud Functions live

## What It Does

Standalone operator package for NSMT livestreams. The goal is a one-command launch for non-technical team members running broadcasts in the field. Contains broadcast overlay HTML, control interfaces, producer graphics views, a local WebSocket server, and Firebase Cloud Functions for authentication, session management, and event creation. The Firebase/YoloBox variants (`yolo-overlay.html`, `yolo-control.html`) replace the local WebSocket server with Firebase RTDB for fully cloud-hosted state sync, enabling remote operation without a local server.

## Key Files

- `nsmt_fox_overlay_ws.html` — Main broadcast overlay (1920x1080), consumed by OBS browser source
- `nsmt_fox_control_ws.html` — Operator control interface for score, clock, team names
- `nsmt-producer-v2.html` — Producer graphics view for on-screen lower-thirds and transitions
- `yolo-overlay.html` — Firebase RTDB-backed overlay for YoloBox/cloud workflows
- `yolo-control.html` — Firebase RTDB-backed control interface (pairs with yolo-overlay)
- `websocket-server.js` — Local Node.js WebSocket server for LAN-based state sync
- `functions/index.js` — 6 Cloud Functions: auth, session tokens, event creation, RTDB management
- `firebase.json` — Firebase Hosting + Functions + RTDB configuration
- `database.rules.json` — Firebase Realtime Database security rules

## Shared Concepts

- [Firebase](../systems/firebase.md) — RTDB for game state, Hosting for overlay/control, Cloud Functions for auth
- [WebSocket Protocol](../systems/websocket-protocol.md) — Local WS server message format shared with Fastbreak V2
- [NSMT Brand](../design/nsmt-brand.md) — Colors, typography, and logos used in overlay and control UI
- [OBS Configuration](../systems/obs-configuration.md) — Scene layout and browser source settings for overlays
- [Cloud Functions](../systems/cloud-functions.md) — Details on the 6 deployed Cloud Functions
- [IAM and Auth](../systems/iam-and-auth.md) — GCP service accounts and permissions for Firebase deploy

## Recent Changes

- 2026-04-06: 6 Cloud Functions deployed as 1st Gen to Firebase. IAM roles fixed (`storage.objectAdmin` + `artifactregistry.writer` added to service account).
- 2026-04-06: Web-based Create Event page added for setting up new events with copy-able overlay/control URLs.
- 2026-04-06: Firebase RTDB integration active for YoloBox overlay and control variants.
- 2026-04-06: Database rules updated — removed unsupported `_comment` field.

## Open Issues

- 1st Gen vs 2nd Gen Cloud Functions API mismatch needs resolution before next deploy. Current functions use `functions.https.onRequest` (1st Gen) but project may need migration to 2nd Gen for improved scaling and pricing.
- Overlay and control interface designs still being finalized — visual parity with Fastbreak V2 overlay not yet achieved.
- Local WebSocket server and Firebase RTDB paths need to be kept in sync as protocol evolves.
