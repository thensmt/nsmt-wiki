---
title: The Fastbreak App (Ticketing)
type: project
status: active
created: 2026-04-06
updated: 2026-04-06
tags:
  - ticketing
  - react
  - aws
  - stripe
---

# The Fastbreak App (Ticketing)

**Repo:** `thensmt/little-rock`
**Location:** `~/Downloads/Claude/little-rock/`
**Stack:** React 18 + Vite, Firebase Auth (Google Sign-In), React Router, Tailwind CSS, AWS Lambda + DynamoDB + Stripe + SES, CloudFormation
**Status:** Active development. Not yet deployed to AWS.

## What It Does

Sports ticketing and event experience platform for small tournament organizers — AAU, youth sports, showcases, and similar events. Provides secure ticket sales with QR codes, game schedules and brackets, court assignments tied to tickets, team rosters, and ticket purchase history. The event detail page serves as each attendee's "home base" during an event, consolidating everything they need in one view. The check-in flow is designed for iPad PWA with a QR scanner at venue entry.

## Key Screens

- **Discovery** — Event listing and search for upcoming tournaments
- **Event Hub** — Attendee home base: schedules, brackets, court assignments, rosters, attendance tracking
- **Checkout** — Stripe-powered ticket purchase flow
- **My Tickets** — Purchase history and active ticket QR codes

## Shared Concepts

- [Kinetic Championship](../design/kinetic-championship.md) — Design system for the ticketing app

## Design: The Kinetic Championship

Dark arena aesthetic built for the energy of live sports:

- **Colors:** Deep purple `#552583`, black `#131313`, silver `#c6c6c6`, gold `#ecbf7b`
- **Typography:** Lexend (headlines), Manrope (body), Space Grotesk (labels/data)
- **Shape:** `0px` border-radius throughout, no drop shadows
- **Depth:** Tonal depth layering using subtle background color shifts instead of elevation

## Recent Changes

- Active frontend development with React 18 + Vite.
- Firebase Auth with Google Sign-In integrated for user accounts.
- AWS backend architecture defined: Lambda functions, DynamoDB tables, Stripe integration, SES for email confirmations.

## Open Issues

- Not yet deployed — CloudFormation stack has not been provisioned.
- iPad PWA check-in experience with QR scanner is planned but not yet built.
- AWS infrastructure (Lambda, DynamoDB, SES) needs initial deploy and testing.
