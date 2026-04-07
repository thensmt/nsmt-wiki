---
title: Firebase
type: system
status: active
created: 2026-04-06
updated: 2026-04-06
tags:
  - firebase
  - gcp
  - rtdb
  - hosting
---

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

## Goal: Eliminate MacBook Pro from Broadcast Workflow

The Firebase migration goal is to remove the need for a local MacBook Pro server during broadcasts. With Firebase RTDB + Hosting + Cloud Functions, the YoloBox Extreme loads the overlay URL directly, and the iPad controls via the hosted control hub URL. No local server needed.

### What's Left

1. Resolve 1st Gen vs 2nd Gen function mismatch before next deploy
2. Finalize overlay design for hosted version
3. Finalize control hub for hosted version
4. Push to GitHub Pages or Firebase Hosting for YoloBox integration

## Open Issues

- **v1 vs v2 API mismatch:** Deployed functions are 1st Gen (firebase-functions v5), but code on disk uses v2 API (firebase-functions v7 / firebase-admin v13). See [Cloud Functions](cloud-functions.md) for resolution options.

## Cross-References

- [Cloud Functions](cloud-functions.md) — details on the 6 deployed functions
- [IAM and Auth](iam-and-auth.md) — GCP service accounts and permissions
- [Project Austin](../projects/austin.md) — primary consumer of Firebase services
- [Fastbreak V2](../projects/fastbreak-v2.md) — remote overlay mode uses Firebase
- [ADR-002: Firebase vs WebSocket](../decisions/adr-002-firebase-vs-websocket.md) — decision to support both transports
