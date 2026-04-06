# Firebase

**GCP Project:** sincere-nirvana-436014-v9 ("The NSMT")
**Project ID:** 417098775531
**RTDB:** https://nsmt-scorebug.firebaseio.com
**Hosting:** sincere-nirvana-436014-v9.web.app
**Auth owner:** david@nsmtsports.com

## What It Does

Firebase provides the real-time database, hosting, and Cloud Functions infrastructure for NSMT. It powers both Project Austin's scorebug system and Livestream V2's remote operation mode (YoloBox).

## Services in Use

- **Realtime Database** — game state storage and real-time sync for overlays and controls
- **Hosting** — serves overlay and control HTML for remote/YoloBox operation
- **Cloud Functions** — 6 functions deployed as 1st Generation on 2026-04-06

## Used By

- [Project Austin](../projects/austin.md) — scorebug overlay and control panels
- Livestream V2 — remote overlay mode

## Open Issues

- **v1 vs v2 API mismatch:** Functions were deployed as 1st Generation but some code may expect 2nd Generation APIs. Needs resolution.

## Cross-References

- [Cloud Functions](cloud-functions.md) — details on the 6 deployed functions
- [IAM and Auth](iam-and-auth.md) — GCP service accounts and permissions
- [Project Austin](../projects/austin.md) — primary consumer of Firebase services
- [ADR-002: Firebase vs WebSocket](../decisions/adr-002-firebase-vs-websocket.md) — decision to support both transports
