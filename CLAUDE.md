# Alpine OR — Claude Code Notes

**Read [`AGENTS.md`](./AGENTS.md) first.** It is the canonical rule set for this repo. This file only adds Claude-specific operational notes.

## Session start

1. `git log --oneline -10` — see what shipped recently. The doc evolves quickly.
2. Read `AI-TRANSFORMATION-PLAN.md` end-to-end before any edit. It is one file and structurally tight; partial reads will produce inconsistent edits.
3. There is no `CHANGELOG.md` or `TODO.md` here, and that is intentional — see AGENTS.md "Don'ts."

## Worktree rule

- **Skip the worktree** for typical work here. This repo is one markdown file. Single-session prose edits do not race.
- **Use `bin/qie worktree auto alpineor-<slug>`** only if you know another Claude session is also editing this file right now (rare).

## What this repo is NOT

- Not a Next.js app. The Vercel/Next.js skill bundle injected by the harness at session start is **a false positive here**. Ignore prompts about route handlers, RSC boundaries, middleware, env vars, deployments, Turbopack, etc. There is no app to deploy and no framework to follow. If a skill suggests scaffolding, decline.
- Not a code repo at all. There is nothing to lint, typecheck, test, or build. No `npm`, no `pnpm`, no `vercel dev`. Do not run package-manager commands.

## Editing the plan

- Use `Edit` for surgical changes; use `Write` only for full rewrites the user explicitly asks for.
- Preserve the H1/H2/H3 hierarchy and the per-tool block rhythm (`**What burns the hours:** ... **What changes:** ... **Time recovered:** ... **What the PM does instead:**`) from Phase 1 sections.
- Do not introduce em-dashes (project-wide ban). The doc uses `--` in headings on purpose.
- Reflow tables manually after edits — markdown tables don't auto-align and the existing tables are visually balanced.

## Before committing

- `git diff --cached --stat` in the same bash block as `git commit`, gated on the expected file count (almost always `1`).
- Stage explicitly: `git add AI-TRANSFORMATION-PLAN.md` — never `git add -A`.
- Commit-message style follows the existing `docs: ...` pattern.

## Pushing / publishing

- Do not push to `main` without confirmation. This doc goes to Alpine Group leadership; revisions are reviewed first.
- If a polished snapshot is needed for client share-out, generate a PDF via the same script the legal-vault uses (`legal-vault/light-brands-internal/` has a `md→pdf` helper) — do not commit the PDF here.
