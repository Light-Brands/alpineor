# Alpine OR — Agent Rules

## What this is

A **proposal repo**, not an application. The entire deliverable is `AI-TRANSFORMATION-PLAN.md` — Light Brands' sales pitch to Alpine Group / Alpine OR (a luxury-construction owner's representative firm with 100+ completed projects). There is no code, no build system, no runtime. Edits here are prose work on a live client-facing document. Treat it like a legal-vault artifact that happens to live in `clients/`.

## Stack

- Markdown only. No package manager, no lockfile, no CI.
- Rendering surface: the doc gets pasted/exported to PDF or shared raw with Alpine Group leadership.

## Where things live

```
alpineor/
├── AI-TRANSFORMATION-PLAN.md   # THE deliverable — 2x → 10x → 100x roadmap, v2.0
├── AGENTS.md                    # this file
└── CLAUDE.md                    # Claude-specific session notes
```

That's it. No `src/`, no `package.json`, no `.env`. If you find yourself wanting to scaffold app structure here, stop — you're in the wrong repo.

## Current focus

Per `git log` (most recent first):

1. `f22d42a docs: rewrite plan as progressive 2x → 10x → 100x roadmap` — v2.0 reframe from a flat 12-item list into an earned three-phase progression. This is the current pitch.
2. `a0f89e5 docs: Alpine OR AI transformation plan — 12 opportunities across 4 tiers` — v1.0 (superseded; the 12 opportunities now live inside the three phases).

The active narrative: **2x first (weeks 1-6, no process change), 10x second (months 2-6, AI-native rebuild), 100x last (months 6-12+, platform plays).** Each phase is gated on the previous phase proving out. Do not regress to flat-list framing.

## Conventions (observed in the doc)

- **Voice:** confident, understated, no hype words. Section openers describe what burns the client's hours, then what changes, then time recovered, then what the PM does instead.
- **Phase tables** at the end of each phase summarize tools/systems with "compound effect" or "PM role" columns. Match this rhythm if extending.
- **No em-dashes in prose.** Per user-wide standard (`feedback_dash_ban`). The plan currently uses `--` as a substitute in headings (e.g. `Alpine OR -- AI Transformation Plan`, `Phase 1 -- 2x`). Keep that pattern.
- **No "institutional grade/quality/caliber"** language. Per `feedback_voice_no_institutional`. Already absent — keep it that way.
- **Headers:** H1 once at top, H2 for phase boundaries, H3 for individual tools/systems, bold callouts (`**What burns the hours:**`) inside each tool block.
- **Numbers stay concrete.** "3-7 hours/week per PM," "100+ projects," "$500k+ bathrooms." No vague "significant" or "transformative."

## Gotchas

- **The numbered tool list is continuous across phases.** Tools 1-3 are Phase 1, 4-7 are Phase 2, 8-12 are Phase 3. Don't restart numbering inside a phase, and don't insert a new tool without renumbering everything below it.
- **Phase 3 is explicitly tentative** ("not a plan, a conversation we earn the right to have"). If editing Phase 3 ideas, keep the conditional framing — these are not commitments.
- **Light Brands self-description** at the bottom cites "107 AI agents and 204+ workflows." If QIE counts change materially, update that line. Cross-check against the QIE hub `CLAUDE.md` agent count (currently states 99 agents / 180+ workflows there — there is already a small drift; reconcile with the user before publishing externally).
- **Client name varies in the doc:** "Alpine OR" (short), "Alpine Group / Alpine OR" (formal header), "Alpine" (casual). All three are intentional. Don't normalize.

## Don'ts (hard bans for this repo)

- Don't add `package.json`, `node_modules`, build configs, or any runtime scaffolding. If a future engagement actually builds the systems described here, that goes in a **new repo**, not this one.
- Don't commit any client-supplied data (project lists, contractor names, budgets, addresses). The plan is generic and stays generic until a signed engagement.
- Don't push to `main` without the user's review — this is a client-facing doc and revisions get reviewed before they leave.
- Don't replace `--` with em-dashes anywhere in prose, even when "fixing" formatting.
- Don't add a `CHANGELOG.md` unless asked. The git log is the changelog for a one-doc repo.

## Secrets

Nothing sensitive should ever land here. No `.env*`, no API keys, no Alpine-internal financials, no contractor lists, no client PII. If the user pastes Alpine internal data for context, keep it in scratch/local notes — don't commit it.
