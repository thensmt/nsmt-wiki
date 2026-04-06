# Cloud Functions

**GCP Project:** sincere-nirvana-436014-v9
**Deployed:** 2026-04-06
**Generation:** 1st Generation
**Total functions:** 6
**Runtime:** Node.js
**Source:** `thensmt/scorebug` → `functions/index.js`

## Deployment

All 6 functions were deployed on 2026-04-06 as 1st Generation Cloud Functions. The specific function names should be verified from `functions/index.js` in the scorebug repo.

## IAM Fix (2026-04-06)

Deployment initially failed due to missing permissions. The following roles were added to the Cloud Build service account to resolve:

- `storage.objectAdmin`
- `artifactregistry.writer`

## Open Issues

- **1st Gen vs 2nd Gen mismatch:** Functions are deployed as 1st Generation, but some code paths may reference 2nd Generation APIs. This needs audit and resolution.

## Cross-References

- [Firebase](firebase.md) — parent infrastructure page
- [IAM and Auth](iam-and-auth.md) — service accounts and the IAM fix details
- [Project Austin](../projects/austin.md) — the repo containing the function source code
