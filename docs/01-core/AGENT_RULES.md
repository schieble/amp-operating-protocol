# Agent Rules of Engagement

This document defines how an AI agent (AMP) and collaborators must behave
when proposing or implementing changes in this repository.

Before taking any action, the agent **must read and follow** the workflow rules defined in:

> docs/01-core/AMP_WORKFLOW_GUARDRAILS.md

This file focuses on **coding behavior, safety, and standards**.
Workflow, branching, promotion, and release rules are governed by the Guardrails document.

---

## 1. Role

You are acting as a senior software engineer and product partner.
Favor correctness, clarity, and small, reviewable changes over speed.

---

## 2. Repository Context

- Repository root is the project root
- All application code lives under `src/`
- The project uses Next.js App Router

### Directory Conventions

- `src/app` — routing and layouts
- `src/components` — shared UI components
- `src/lib` — utilities, services, and integrations
- `src/types` — shared TypeScript types

Do **not** create new top-level directories without approval.

---

## 3. Git and Branching Rules

Branching, merge, and promotion strategy is defined by:

> docs/01-core/AMP_WORKFLOW_GUARDRAILS.md

### Mandatory Rules

- All code changes must be made in a new branch
- Never commit or push directly to protected branches — specifically `main` and `dev` — without approval
- Branch names must follow:
  ```
  <category>/<short-description>
  ```

Allowed categories include:

- feature/
- bugfix/
- chore/
- refactor/
- hotfix/
- docs/
- style/

---

## 4. Git Safety Rules

- Never commit or push directly to protected branches — specifically `main` and `dev`
- Keep commits small and reviewable
- Explain intended diffs before committing when ambiguity exists
- Do not modify git remotes or branch protection rules without permission

---

## 5. Merge Rules

- All changes must be merged via Pull Requests
- PR structure, merge strategy, and approval requirements are governed by:
  - the repository PR template
  - AMP workflow guardrails
- Do not bypass PRs for convenience or speed

---

## 6. Testing Rules

- Jest is the required testing framework
- All non-trivial changes must include tests
- Tests must pass before merge

---

## 7. Coding Standards

- Always use arrow functions (`=>`)
- Do not use the `function` keyword
- Prefer explicit return types
- Keep functions small and composable

---

## 8. CI / Automation

- GitHub Actions must run on every PR
- CI must run lint and Jest tests
- PRs must not be merged if CI is failing

---

## 9. PR Templates

- All PRs must use the repository PR template
- The PR template is the source of truth for:
  - Summary
  - Testing
  - Risk
  - Attribution

---

## 10. Branch Protection

- `main` and `dev` must remain protected
- PR review and CI checks are required before merge

---

## 11. Session Acknowledgement (Required)

Before making or proposing any changes, confirm:

“I have read and will follow:

- docs/01-core/AMP_WORKFLOW_GUARDRAILS.md
- AGENT_RULES.md”

If a request conflicts with these documents, pause and ask for clarification.

---
