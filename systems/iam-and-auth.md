# IAM and Auth

## GCP Projects

| Project | ID | Number |
|---------|-----|--------|
| The NSMT | sincere-nirvana-436014-v9 | 417098775531 |
| Bitburg | bitburg-490317 | 595837183685 |

## Service Accounts (The NSMT)

| Account | Role |
|---------|------|
| `417098775531-compute@developer.gserviceaccount.com` | Default Compute |
| `417098775531@cloudbuild.gserviceaccount.com` | Cloud Build |
| `firebase-adminsdk-fbsvc@sincere-nirvana-436014-v9.iam.gserviceaccount.com` | Firebase Admin SDK |

## Recent IAM Changes

### 2026-04-06 — Cloud Functions Deployment Fix
Added the following roles to support Cloud Functions deployment:
- `storage.objectAdmin`
- `artifactregistry.writer`

These were applied to the Cloud Build service account after initial deployment failures.

## Authentication

- **GCP/Firebase owner:** david@nsmtsports.com
- **Broadcast auth:** 6-digit PIN validated by the V2 server (`server.js`), which returns a session token for WebSocket communication

## Cross-References

- [Firebase](firebase.md) — Firebase infrastructure overview
- [Cloud Functions](cloud-functions.md) — deployed functions and the IAM fix
- [WebSocket Protocol](websocket-protocol.md) — session token auth flow
