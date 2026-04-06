# ADR-001: V2 Fresh Build

**Date:** 2026-03-28
**Status:** accepted

## Context

The V1 broadcast system was functional but had accumulated significant design debt. The old CSS/HTML patterns and code structure did not match the new NSMT Fastbreak design direction coming from Google Stitch exports. Attempting to retrofit V1 would mean fighting legacy patterns at every step.

## Decision

V2 is a complete ground-up rebuild. No code is carried over from V1. Only V1's functionality requirements (what it does) and the WebSocket protocol/state shape are referenced as inputs to the V2 design.

## Consequences

- Slower initial progress but a cleaner architecture aligned with the Fastbreak design system
- V1 at `~/NSMT/livestream/` is kept as reference only
- CSS/HTML patterns must never be copied from V1 to V2
- The WebSocket protocol and game state shape are the only continuity between versions

## Cross-References

- [Livestream V2](../projects/fastbreak-v2.md) — the V2 project built from this decision
