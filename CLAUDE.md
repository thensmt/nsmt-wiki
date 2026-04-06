# NSMT Wiki — LLM Schema

This is the NSMT knowledge base — a persistent, compounding wiki maintained by LLM agents across all `thensmt/` projects. Based on [Karpathy's LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

## Three Layers

1. **Raw sources** — immutable inputs in `sources/`. The LLM reads but never modifies these.
2. **The wiki** — all other markdown files. The LLM owns this layer entirely. It creates, updates, and cross-references pages.
3. **This schema** — tells the LLM how to maintain the wiki.

## Directory Structure

```
CLAUDE.md              ← You are here (schema)
index.md               ← Master index of all pages (content-oriented)
log.md                 ← Chronological record of all operations (append-only)

projects/              ← One page per project/repo
  austin.md            ← Project Austin (thensmt/scorebug)
  fastbreak-v2.md      ← Livestream V2 (thensmt/nsmt-fastbreak)
  fastbreak-app.md     ← The Fastbreak App (thensmt/little-rock)
  bitburg.md           ← Marketplace (thensmt/bitburg)
  content-pipeline.md  ← Content system (thensmt/nsmt-content-pipeline)

systems/               ← Technical systems and infrastructure
  firebase.md          ← Firebase RTDB, Hosting, Cloud Functions
  websocket-protocol.md ← WS protocol shared across projects
  obs-configuration.md ← OBS scenes, sources, hotkeys, output settings
  cloud-functions.md   ← Individual function docs, deploy status
  iam-and-auth.md      ← GCP IAM, service accounts, auth flows

broadcast/             ← Everything about live production
  equipment/           ← One page per equipment category
  roles/               ← One page per broadcast role
  runbooks/            ← Step-by-step procedures
  events/              ← Post-event reports (one per broadcast)

design/                ← Design systems and brand
  nsmt-brand.md        ← Master brand (colors, typography, logos)
  fastbreak-design-system.md ← Broadcast UI design tokens
  kinetic-championship.md    ← Ticketing app design tokens
  design-tokens.md     ← Cross-system comparison

decisions/             ← Architecture Decision Records (ADRs)
  adr-NNN-title.md     ← One per significant decision

sources/               ← Raw source summaries (immutable)
```

## Page Templates

### Project Page
```markdown
# Project Name

**Repo:** `thensmt/repo-name`
**Location:** local path
**Stack:** key technologies
**Status:** current state

## What It Does
One paragraph.

## Key Files
- `path/to/file` — what it does

## Shared Concepts
Links to systems/ and design/ pages that this project uses.

## Recent Changes
Bullet list of significant recent changes with dates.

## Open Issues
Known bugs, planned work, unresolved decisions.
```

### Equipment Page
```markdown
# Equipment Name

**Model:** full model name
**Qty:** how many owned
**Purchase:** link or price
**Used by:** which broadcast roles

## Specs
Key specifications relevant to NSMT use.

## Configuration
Current setup/settings for NSMT broadcasts.

## Known Issues
Problems encountered, workarounds, lessons learned.

## Cross-References
Links to related equipment, roles, and runbook pages.
```

### Role Page
```markdown
# Role Name

**Required for minimum crew:** yes/no
**Equipment:** list with links to equipment pages
**Can double as:** which other roles this person can cover

## Responsibilities
What this person does during a broadcast.

## Setup Checklist
Pre-game setup steps.

## During Broadcast
What to monitor, common actions.

## Common Issues
Troubleshooting specific to this role.
```

### Architecture Decision Record (ADR)
```markdown
# ADR-NNN: Title

**Date:** YYYY-MM-DD
**Status:** proposed | accepted | superseded
**Supersedes:** ADR-NNN (if applicable)

## Context
What prompted this decision.

## Decision
What was decided.

## Consequences
What changes as a result. Trade-offs accepted.

## Cross-References
Links to affected project and system pages.
```

### Event Report
```markdown
# Event Name — YYYY-MM-DD

**Venue:** location
**Crew:** who filled which roles
**Stream:** where it was broadcast

## What Went Well
Bullet list.

## What Went Wrong
Bullet list with links to equipment/role pages updated as a result.

## Lessons Learned
Actionable items. Each should link to the page that was updated.

## Stats
Viewership, duration, technical metrics if available.
```

## Cross-Reference Conventions

- Use relative markdown links: `[Firebase](../systems/firebase.md)`
- When mentioning a concept that has its own page, always link it
- Every page should have at least one inbound link from another page
- The index.md tracks all pages — update it on every create/delete

## Operations

### Ingest
When a new source is added to `sources/` or new information is provided:

1. Read the source material
2. Discuss key takeaways with the user
3. Write or update a summary in the appropriate wiki section
4. Update `index.md` with any new pages
5. Update cross-references on related pages (check 2-3 most related pages)
6. Append an entry to `log.md`

A single source may touch 5-15 wiki pages. Prefer updating existing pages over creating new ones.

### Query
When answering questions against the wiki:

1. Read `index.md` to find relevant pages
2. Read the relevant pages
3. Synthesize an answer with citations to specific wiki pages
4. If the answer reveals a valuable synthesis, offer to file it as a new wiki page

### Lint
Periodically health-check the wiki:

- Orphan pages with no inbound links
- Stale claims contradicted by current code or recent deploys
- Missing cross-references between related pages
- Important concepts mentioned but lacking their own page
- Equipment specs that may have changed
- Cloud infrastructure state vs. what's documented

## Rules

- The wiki explains *decisions, trade-offs, and context* — it does not duplicate code
- Equipment specs, brand colors, and infrastructure state belong here; implementation code does not
- Every page must be linked from at least one other page and from `index.md`
- `log.md` is append-only — never edit or delete entries
- `sources/` files are immutable — never modify after initial creation
- Dates are always absolute (YYYY-MM-DD), never relative
- Keep pages concise — a page that's too long should be split
- When in doubt, update an existing page rather than creating a new one

## GitHub Organization

All repos are under `thensmt/`:

| Repo | Project |
|---|---|
| `thensmt/scorebug` | Project Austin |
| `thensmt/nsmt-fastbreak` | Livestream V2 |
| `thensmt/little-rock` | The Fastbreak App |
| `thensmt/bitburg` | Bitburg Marketplace |
| `thensmt/nsmt-content-pipeline` | Content Pipeline |
| `thensmt/nsmt-wiki` | This wiki |
