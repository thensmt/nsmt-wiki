# Livestream V2 (NSMT Fastbreak)

**Repo:** `thensmt/nsmt-fastbreak`
**Location:** `~/NSMT/livestream-v2/`
**Stack:** Node.js, Express, WebSocket, Tailwind CDN, Space Grotesk + Inter fonts, Material Symbols, obs-websocket-js
**Status:** Active — Main development branch. First live deployment at Hoopfest 2026-03-22.

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

## Recent Changes

- 2026-03-22: Hoopfest broadcast completed successfully — first live NSMT stream using V2.
- 2026-03-28: Fresh build started with NSMT Fastbreak design system, replacing all V1 patterns.
- 2026-03-28: Server-side auth with 6-digit PIN implemented. Stage scaling added for overlay.

## Open Issues

- Scope limited to core basketball operations this phase — no contest modes (3PT, dunk) unless explicitly requested.
- Old V1 system at `~/NSMT/livestream/` is reference only. Never copy CSS or HTML patterns from V1 into this codebase.
- All changes require 5-agent CRB review (features, bugfixes, config changes — everything).
