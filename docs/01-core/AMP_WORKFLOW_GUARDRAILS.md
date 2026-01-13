# AMP Workflow Guardrails

This document defines **non-negotiable rules and operating constraints**
that AMP must follow when assisting with development, Git, and GitHub
workflows.

> **Terminology note:** In this document, "AMP" refers to the AI development tool.
> These rules are defined by the AMP Operating Protocol and enforced on the tool.

This file acts as a **governor** for AMP behavior.
If a request conflicts with these rules, AMP must **pause and ask for clarification**
or **refuse and explain why**.

---

## 1. Repository & Branch Model (Authoritative)

AMP must assume the following branch semantics at all times:

- `main` = **Production**
  - Protected
  - PR-only
  - No direct commits
- `dev` = **Integration**
  - All work merges here first
  - PR-only
- Feature branches:
  - `feature/<issue#>-slug`
  - `bugfix/<issue#>-slug`
  - `chore/<issue#>-slug`

### Hard rules

- AMP must NEVER suggest committing directly to `main`
- AMP must NEVER suggest bypassing PRs
- AMP must ALWAYS assume work branches are created from `dev`
- AMP must ALWAYS assume merges into `dev` and `main` happen via PR

---

## 2. PR & Merge Strategy (Squash-First)

### Default merge behavior

- **Squash merge is the default and recommended strategy**
- One PR = one logical change = one commit on `dev` or `main`

### AMP behavior

- AMP should optimize suggestions for squash merges
- AMP should assume selective promotion relies on single-commit PRs
- AMP must include `Closes #<issue>` in PR body examples

### Attribution handling

- If collaboration is implied, AMP must suggest:
  ```
  Co-authored-by: Name <email>
  ```
- AMP must NOT invent co-authors

---

## 3. Selective Promotion Rules (Critical)

Selective promotion is a **first-class workflow**.

### When selective promotion applies

- `dev` contains work not ready for production
- Only specific fixes/features should be promoted to `main`

### Required promotion method

1. Create a branch from `main`
   ```
   promote/<issue#>-slug
   ```
2. Cherry-pick **only the relevant commit(s)** from `dev`
3. Open PR into `main`
4. Merge via PR
5. Back-merge `main` into `dev`

### Hard rules

- AMP must NOT suggest merging `dev → main` if user indicates partial promotion
- AMP must NOT cherry-pick merge commits unless explicitly instructed
- AMP must ALWAYS remind to merge `main` back into `dev` after selective promotion

---

## 4. Hotfix Rules (Emergency Only)

Hotfixes are allowed only when production is broken.

### Required hotfix flow

1. Branch from `main`
   ```
   hotfix/<issue#>-slug
   ```
2. Fix + commit
3. PR to `main`
4. Merge
5. Merge `main` back into `dev`

### AMP behavior

- AMP must confirm production impact before suggesting hotfix flow
- AMP must discourage hotfixes for convenience or speed

---

## 5. Issue Discipline (Mandatory)

### Rules

- All work merged to `dev` or `main` must have a GitHub Issue
- Issues are the **unit of work**
- Markdown files are NOT task trackers
- Feature branches in active development (not yet merged to `dev`) may exist without an issue

### AMP behavior

- AMP must ask for an issue number before merging to `dev` or `main`
- AMP should NOT require an issue for local feature branch commits
- AMP may help DRAFT issues, but must not claim to create them
- AMP must align issue output to existing GitHub issue templates

---

## 6. ADR (Architecture Decision Record) Guidance

### When an ADR is REQUIRED

AMP must recommend an ADR when a change:

- Introduces or replaces a vendor
- Changes system boundaries or data ownership
- Introduces long-term architectural constraints
- Affects multiple subsystems
- Trades off latency, cost, security, or reliability

### When an ADR is NOT required

- Small bug fixes
- Refactors with no external behavior change
- Incremental improvements inside an existing architecture

### AMP behavior

- AMP must ask: “Does this require an ADR?” when ambiguity exists
- AMP must NOT force ADRs for normal bug fixes

---

## 7. Release Hygiene & Verification

### Before merging to `main`

AMP should remind the user to confirm:

- Build passes locally (`npm run build` or equivalent)
- Relevant tests pass
- Issue has `Closes #<issue>` in PR body
- Risk level is understood

### After merging to `main`

AMP should recommend:

- Verification in target environment (if applicable)
- Closing the issue if not auto-closed
- Updating release notes if the change is user-visible

---

## 8. PR Review & Merge Authority

### Hard rules

- **AMP must NEVER execute `gh pr merge` or merge PRs directly**
- AMP may create PRs (`gh pr create`) but must stop and wait for human review
- All PR merges happen in GitHub after human approval
- AMP must not use `--auto` flag to queue automatic merges

### AMP behavior

- After creating a PR, AMP must pause and inform the user the PR is ready for review
- AMP should provide the PR URL for the user to review and merge
- AMP may respond to review feedback and push fixes, but must not merge

---

## 9. CodeRabbit Integration Expectations

AMP must assume:

- CodeRabbit is used for automated PR review
- CodeRabbit comments count as review feedback

### AMP behavior

- AMP should encourage responding to CodeRabbit comments before merge
- AMP should avoid suggesting merge if unresolved review comments exist
- AMP should assume PR template sections exist and should be filled

---

## 10. CLI-First Preference

### Preferred tools

- `git`
- `gh` (GitHub CLI)

### AMP behavior

- Prefer CLI commands over GitHub UI instructions
- Show exact commands when possible
- Avoid GUI-only steps unless unavoidable

---

## 11. Refusal & Clarification Rules (Important)

AMP must **pause or refuse** when:

- Asked to bypass PRs
- Asked to commit directly to `main`
- Asked to merge PRs directly (use `gh pr merge` or similar)
- Asked to track execution in Markdown
- Asked to promote partial changes via `dev → main` merge

In these cases, AMP must:

1. Explain why the request violates workflow
2. Propose a compliant alternative

---

## 12. Default Question Set (When Context Is Missing)

If critical context is missing, AMP should ask:

1. Issue number?
2. Target branch (`dev` or `main`)?
3. Is this a selective or batch promotion?
4. Does this change affect architecture?
5. Is production currently impacted?

---

## 13. Prime Directive

> **Clarity over speed.  
> PRs over pushes.  
> Issues over memory.  
> Clean history over convenience.**

If there is a conflict between speed and correctness,
AMP must favor correctness.

---

## How to Use This File

When starting an AMP session, instruct AMP:

> “Read and follow the rules in  
> `docs/01-core/AMP_WORKFLOW_GUARDRAILS.md`  
> before providing assistance.”

AMP should treat this document as authoritative.

---
