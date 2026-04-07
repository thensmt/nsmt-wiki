---
title: Cloud Functions
type: system
status: active
created: 2026-04-06
updated: 2026-04-06
tags:
  - firebase
  - cloud-functions
  - gcp
  - iam
---

# Cloud Functions

**GCP Project:** sincere-nirvana-436014-v9
**Deployed:** 2026-04-06
**Generation:** 1st Generation (deployed with firebase-functions v5)
**Total functions:** 6
**Runtime:** Node.js 20
**Source:** `thensmt/scorebug` → `functions/index.js`
**Branch:** `firebase-yolobox`

## Functions

| Function | Purpose |
|----------|---------|
| `createEvent` | Create event with hashed operator/owner PINs |
| `authenticate` | PIN validation + session creation with custom Auth token |
| `renewSession` | Extend session TTL |
| `revokeOperator` | Owner revokes operator session |
| `rotatePin` | Owner changes operator or owner PIN |
| `registerAsset` | Register Cloud Storage URL in RTDB |

## IAM Fix (2026-04-06)

Deployment initially failed due to missing permissions. The following roles were added to resolve:

| Role | Service Account |
|------|----------------|
| `storage.objectAdmin` | `417098775531-compute@developer.gserviceaccount.com` |
| `artifactregistry.writer` | Both `417098775531-compute@developer.gserviceaccount.com` and `417098775531@cloudbuild.gserviceaccount.com` |

These were required for Cloud Build to push container images during function deployment.

## Open Issues

- **1st Gen vs 2nd Gen mismatch:** The **deployed** functions are 1st Gen (firebase-functions v5). The **code on disk** (`functions/index.js`) has been converted to v2 API (`firebase-functions/v2/https`, `onCall(async (request) => {})`) using firebase-functions v7 and firebase-admin v13. The next deploy will fail with "Upgrading from 1st Gen to 2nd Gen is not yet supported" unless:
  - Functions are deleted first and redeployed as 2nd Gen, OR
  - Code is reverted to v1 API with firebase-functions v5

## Cross-References

- [Firebase](firebase.md) — parent infrastructure page
- [IAM and Auth](iam-and-auth.md) — service accounts and the IAM fix details
- [Project Austin](../projects/austin.md) — the repo containing the function source code
