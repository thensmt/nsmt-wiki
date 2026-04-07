---
title: Livestream V2 (NSMT Fastbreak)
type: project
status: active
created: 2026-04-06
updated: 2026-04-06
tags:
  - broadcast
  - websocket
  - obs
  - design-system
---

# Livestream V2 (NSMT Fastbreak)

**Repo:** `thensmt/nsmt-fastbreak`
**Location:** `~/NSMT/livestream-v2/`
**Stack:** Node.js, Express, WebSocket, Tailwind CDN, Space Grotesk + Inter fonts, Material Symbols, obs-websocket-js
**Status:** Active — Main development branch. V1/prototype was used at Hoopfest 2026-03-22; V2 fresh rebuild started 2026-03-28.

## What It Does

Ground-up rebuild of the NSMT broadcast system, started 2026-03-28. This is fresh code — NOT a reskin of V1. Handles full game state management, broadcast overlay rendering at 1920x1080, a control hub for operators, OBS integration via obs-websocket-js, and server-side authentication with a 6-digit PIN. The Express server manages WebSocket connections, proxies OBS commands, serves health endpoints, and persists game state to disk with automatic backup. All changes to this codebase require 5-agent CRB (Change Review Board) review.

## Key Files

- `server.js` — Express + WebSocket server, OBS proxy, health endpoint, state archive, 6-digit PIN auth
- `public/overlay.html` — Broadcast overlay (1920x1080 browser source for OBS)
- `public/control-hub.html` — Main operator control interface
- `public/golden-hub.html` — Alternative control hub layout
- `public/ws-client.js` — Shared WebSocket client with offline message queue and automatic reconnect
- `public/fastbreak.css` — Design tokens for the NSMT Fastbreak design system
- `game_state.json` — Persisted game state with `.bak` automatic backup

## Shared Concepts

- [WebSocket Protocol](../systems/websocket-protocol.md) — Message types, state sync, offline queue behavior
- [OBS Configuration](../systems/obs-configuration.md) — Scene layout, source naming, hotkey bindings, obs-websocket-js integration
- [Fastbreak Design System](../design/fastbreak-design-system.md) — Design tokens, component patterns, Space Grotesk + Inter typography
- [NSMT Brand](../design/nsmt-brand.md) — Master brand reference (colors, typography, logos)

## Recent Changes

- 2026-03-22: [Hoopfest](../broadcast/events/hoopfest-2026-03-22.md) broadcast completed successfully — first live NSMT stream using the V1/prototype system.
- 2026-03-28: After Hoopfest, decision made to do a ground-up rebuild as V2 rather than retrofit V1. Fresh build started with [NSMT Fastbreak design system](../design/fastbreak-design-system.md), replacing all V1 patterns.
- 2026-03-28: Server-side auth with 6-digit PIN implemented. Stage scaling added for overlay.

## Launch Procedure ("start the fastbreak")

To start the Fastbreak system for a broadcast:

1. Kill any existing server on port 8000: `lsof -ti:8000 | xargs kill -9 2>/dev/null`
2. Start server: `cd ~/NSMT/livestream-v2 && node server.js &`
3. Open Chrome with login page + overlay: `open -a "Google Chrome" "http://localhost:8000/"` then `open -a "Google Chrome" "http://localhost:8000/overlay.html"`
4. Get LAN IP: `ipconfig getifaddr en0`

### URLs

| Interface | URL |
|-----------|-----|
| Control Hub (Mac) | `http://localhost:8000/control-hub.html` |
| Control Hub (iPad) | `http://<LAN_IP>:8000/control-hub.html` |
| Stats Entry (iPad) | `http://<LAN_IP>:8000/stats-entry.html` |
| Roster Manager | `http://<LAN_IP>:8000/roster-manager.html` |
| Asset Manager | `http://<LAN_IP>:8000/asset-manager.html` |
| Overlay (OBS) | `http://localhost:8000/overlay.html` (1920x1080 browser source) |

5. Verify health: `curl http://localhost:8000/health`
6. OBS setup: Tools > WebSocket Server Settings > Enable on port 4455

## Change Review Board (CRB)

ALL changes to this codebase require 5-agent CRB review before implementation -- features, bugfixes, refactors, config changes, infrastructure. After planning is complete but before implementation, 5 CRB agents review in parallel and vote GREEN / YELLOW / RED.

### CRB Roles (permanent)

1. **Software Architecture & Development Lead**
2. **Cybersecurity Expert**
3. **Frontend Design & UX Lead**
4. **QA/Testing & Reliability Engineer**
5. **DevOps & Infrastructure Lead**

Development teams present their decisions to the CRB. Required changes (YELLOW/RED items) must be incorporated before implementation begins. CRB findings are documented in the plan file under a "CRB Review Results" section.

## Agent Team Workflow

When deploying agents for code changes to this project:

1. **Team Leader Report (Before)** -- summarize what will be changed, which files, and the approach
2. **Research First** -- explore the codebase before making changes; understand existing patterns
3. **SME Review** -- after changes, review from senior dev, QA tester, and UI/UX designer perspectives
4. **Fix After Research** -- never fix blindly; research root causes first
5. **Design Quality** -- 60px+ touch targets, proper spacing, visual hierarchy, production-ready aesthetics
6. **Team Leader Report (After)** -- final summary of what was done, what was fixed, known issues

## Open Issues

- Scope limited to core basketball operations this phase -- no contest modes (3PT, dunk) unless explicitly requested.
- Old V1 system at `~/NSMT/livestream/` is reference only. Never copy CSS or HTML patterns from V1 into this codebase.
- All changes require 5-agent CRB review (features, bugfixes, config changes -- everything).
