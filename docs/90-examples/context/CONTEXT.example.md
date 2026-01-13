# Project Context Handoff

## Project

- Name: Example Project
- Stack: Next.js (App Router), TypeScript, Jest, GitHub Actions
- Auth: Clerk (with Organizations)
- Database: PostgreSQL (Neon) with Prisma ORM
- UI: Tailwind CSS + shadcn/ui
- Repo Structure: `src/` directory used

## Decisions Locked In

- Use `src/` for all application code
- Arrow functions only (no `function` keyword)
- Branch-based workflow with required PRs
- Jest required for non-trivial changes
- GitHub Actions runs lint + typecheck + tests on every PR
- `main` branch protected
- PRDs and task files stored in `docs/software-engineering/example-project/features/`

## Documentation Structure

- `docs/ai-dev-tasks/` — Agent rules and workflow guides
- `docs/branding/` — Brand assets and guidelines
- `docs/software-engineering/example-project/` — Example Project project docs (PRD, schema, roadmap)
- `docs/software-engineering/example-project/features/` — Feature PRDs, tasks, and research

## Handoff Document Convention

Handoff documents track session state and next steps. Located in feature `debugging/` folders.

**Naming:**
- `CURRENT-HANDOFF-{YYYY-MM-DD}-{HHMM}.md` — Active handoff (only one at a time)
- `ARCHIVED-HANDOFF-{YYYY-MM-DD}-{session}.md` — Previous handoffs

**Rules:**
- When creating a new handoff, rename the previous `CURRENT-*` to `ARCHIVED-*`
- Always include date AND time (24hr format) in current handoff filename
- Only one `CURRENT-*` file should exist per feature area

## Agent Rules

- Agent must read and follow `docs/ai-dev-tasks/AGENT_RULES.md`
- No commits, merges, or dependency additions without approval
- All work happens in a new branch using approved prefixes

## Current Focus

- **Phase 3.6 Dialogue Pipeline** - MERGED TO DEV (PR #32)
- Active handoff: `docs/software-engineering/example-project/features/dialogue-pipeline/debugging/CURRENT-HANDOFF-*.md`
- **Next steps (prioritized):**
  1. Fix webhook tests (pre-existing failures)
  2. Task 13.0: Observability
  3. Reply window feature (conversational continuity)
  4. Automated test harness
  5. Phase 4: Runtime Wiring (Recall integration)
- **Tests:** 1475+ passing

## Open Decisions (Intentionally Pending)

- Deployment target

## Known Constraints

- Context window is tight; prefer small steps
- AI agent (AMP) used for implementation assistance
