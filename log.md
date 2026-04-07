# NSMT Wiki — Log

Chronological record of all operations. Append-only.

---

## 2026-04-06

**Operation:** Initial broadcast section creation
**Pages created (16):**
- `broadcast/equipment/cameras.md`
- `broadcast/equipment/audio.md`
- `broadcast/equipment/video-transport.md`
- `broadcast/equipment/power.md`
- `broadcast/equipment/comms.md`
- `broadcast/roles/tech-director.md`
- `broadcast/roles/camera-operator.md`
- `broadcast/roles/stat-tracker.md`
- `broadcast/roles/announcer.md`
- `broadcast/runbooks/pre-game.md`
- `broadcast/runbooks/live-broadcast.md`
- `broadcast/runbooks/halftime.md`
- `broadcast/runbooks/post-game.md`
- `broadcast/runbooks/troubleshooting.md`
- `broadcast/events/hoopfest-2026-03-22.md`
- `index.md`

**Source:** User-provided broadcast equipment specs, role definitions, runbook procedures, and Hoopfest event notes.
**Cross-references:** All pages cross-linked. Every page has inbound links from at least one other page and from index.md.

## [2026-04-06] lint | First Health Check

Ran initial lint pass. Fixed 24 issues:
- 1 broken link (tech-director.md → sources/)
- 18 missing cross-references added across 10 pages
- 1 timeline contradiction clarified (V2 vs Hoopfest)
- 2 new pages created: systems/castr.md, broadcast/equipment/network.md
- index.md updated with new page entries

## [2026-04-06] ingest | Memory File Sync

Ingested knowledge from 10 Claude Code memory files into the wiki. Changes:

**Pages updated (5):**
- `broadcast/events/hoopfest-2026-03-22.md` — Added crew roles table (iPad primary + MBP backup), player spotlight card success, iPad-as-controller outcome
- `systems/castr.md` — Added server region (ny.castr.io), credential retrieval note, first-used date, why Castr was chosen over Dacast/Vimeo
- `systems/cloud-functions.md` — Added all 6 function names/descriptions, Node.js 20 runtime, firebase-yolobox branch, detailed IAM fix with specific service accounts, detailed v1/v2 mismatch explanation with resolution options
- `systems/firebase.md` — Added "Eliminate MBP from workflow" goal section, what's-left checklist, improved v1/v2 mismatch description
- `projects/bitburg.md` — Added specific credential rotation list (5 secrets: Supabase x3, Clerk x2) with rotation procedure
- `projects/fastbreak-v2.md` — Added launch procedure ("start the fastbreak") with all URLs, CRB process with 5 permanent roles, agent team workflow (6-step)

**Pages created (2):**
- `systems/google-stitch.md` — Google Stitch design tool, export location, known exports, workflow
- `systems/figma.md` — Figma MCP integration (TalkToFigma + Pencil), use cases

**Index updated:** Added Google Stitch and Figma to Systems section.

**Memory files not ingested (rationale):**
- `user_cross_platform.md` — User preference, not wiki-worthy project knowledge
- `feedback_agent_workflow.md` — Incorporated into fastbreak-v2.md (agent workflow section)
- `feedback_crb_process.md` — Incorporated into fastbreak-v2.md (CRB section)

**Source:** Claude Code memory files at `~/.claude/projects/-Users-david-Desktop-Livestream-scorebugfinal/memory/`
