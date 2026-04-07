---
title: Bitburg Marketplace
type: project
status: active
created: 2026-04-06
updated: 2026-04-06
tags:
  - marketplace
  - nextjs
  - supabase
  - stripe
---

# Bitburg Marketplace

**Repo:** `thensmt/bitburg`
**Location:** `~/Desktop/bitburg/`
**Stack:** Next.js 16, TypeScript, React 19.2, Tailwind CSS, shadcn/ui, Supabase PostgreSQL (Prisma ORM), Clerk auth, Stripe payments, Svix webhooks, Vercel deployment
**Status:** Active development, not yet fully deployed.

## What It Does

Media professional marketplace application. Connects media professionals with clients through a modern web platform. Built on Next.js with a Supabase PostgreSQL backend accessed through Prisma ORM, Clerk for authentication, Stripe for payment processing, and Svix for webhook management. Deployed to Vercel.

## Key Files

- Next.js 16 app directory structure with TypeScript
- Prisma schema for Supabase PostgreSQL data model
- Clerk authentication integration
- Stripe payment flows
- Svix webhook handlers

## Shared Concepts

- [Firebase](../systems/firebase.md) — Not used; Bitburg uses Supabase instead (separate infrastructure from other NSMT projects)
- [IAM and Auth](../systems/iam-and-auth.md) — Clerk auth is independent from the GCP/Firebase auth used in other projects

## Recent Changes

- Active development with Next.js 16 and React 19.2.
- shadcn/ui component library integrated for consistent UI.
- Stripe and Svix payment/webhook infrastructure in place.

## Open Issues

- **Credential rotation required before App Store launch.** The following credentials were shared through chat and must be regenerated in each service dashboard before production deployment:
  - Supabase database password
  - Supabase publishable key
  - Supabase secret/service role key
  - Clerk publishable key
  - Clerk secret key

  New credentials should be entered directly into the production environment -- never through chat.
- Full production deployment to Vercel not yet complete.
