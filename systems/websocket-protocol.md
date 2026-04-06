# WebSocket Protocol

**Used in:** Project Austin (`websocket-server.js`), Livestream V2 (`server.js`)
**Port:** 8000 (V2 Express server)

## Protocol Design

The V2 WebSocket implementation uses:

- **Path-based deep merge** — clients send partial state updates keyed by path; the server merges them into the full game state
- **Sequence numbers** — every message carries a sequence number for ordering and conflict detection
- **Offline queue with reconnect** — the client queues messages while disconnected and replays them on reconnection

## Client

`public/ws-client.js` in the V2 repo handles:
- Offline message queuing
- Automatic reconnection with backoff
- Sequence number tracking

## State Persistence

Game state is persisted to `game_state.json` with an atomic `.bak` backup file. On server restart, state is restored from the most recent valid file.

## Authentication

- 6-digit PIN entered by the operator
- Server validates the PIN and returns a session token
- All subsequent WebSocket messages include the session token

## Cross-References

- [Project Austin](../projects/austin.md) — uses WebSocket for local operation
- [Livestream V2](../projects/fastbreak-v2.md) — V2 WebSocket implementation
- [Firebase](firebase.md) — alternative transport for remote/YoloBox operation
- [ADR-002: Firebase vs WebSocket](../decisions/adr-002-firebase-vs-websocket.md) — decision to support both transports
