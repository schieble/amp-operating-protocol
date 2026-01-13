# Human Workflow Setup (Lessons Learned)

This document describes a **proven human workflow** for using the
AMP Operating Protocol effectively on a real production project.

It reflects experience, not mandates.
Adapt it to your own environment.

---

## Purpose

The goal of this workflow is to:

- Maintain human control and accountability
- Maximize visibility into AI actions
- Avoid hidden state inside tools or IDEs
- Balance automation with safety

This setup intentionally favors **transparency over convenience**.

---

## High-Level Environment

The working environment is split into clear responsibilities:

- **AMP / AI Agent**  
  Runs in a large, dedicated terminal window

- **Terminal**  
  Always visible, showing:
  - commands
  - logs
  - test output
  - errors

- **Editor (VS Code)**  
  Used for:
  - browsing the repository
  - reading and editing files
  - navigating code
  - reviewing diffs

The editor is *not* used as a command execution environment.

---

## Editor Usage

In this workflow:

- VS Code is open to the repository at all times
- Files are navigated by clicking and searching
- The integrated terminal is not used
- The AMP or AI extension may be installed but is used sparingly

This avoids:
- Hidden execution context
- Confusion about what ran where
- Over-reliance on IDE automation

---

## Command Execution Model

Not all commands carry the same risk.
This workflow uses **tiered trust**.

---

### High-Impact Commands (Permission Required)

AMP may **propose** but must not execute without approval:

- Git commands (branch creation, commit, push)
- Pull request creation
- Rebases or history rewrites
- Deletions or destructive operations

Before execution:
- AMP explains intent
- The human explicitly approves

---

### Low-Risk Commands (Pre-Approved)

AMP may execute freely during a session:

- Running tests (e.g. Jest)
- Linters and formatters
- Read-only inspection commands
- Build commands with no side effects

These commands are:
- Non-destructive
- Frequently repeated
- Easy to observe

Requiring approval each time adds noise without increasing safety.

---

## Git Discipline

This workflow strictly enforces:

- All work occurs in feature branches
- Protected branches are never modified directly
- All changes flow through Pull Requests
- Reviews are required before merge

AMP handles much of the Git mechanics,
but **never without explicit permission** for high-impact actions.

---

## Why This Worked Well

This setup consistently provided:

- Clear visibility into AI behavior
- Fewer accidental mistakes
- Better review quality
- Easier debugging
- Strong alignment with guardrails

It prevented “autopilot” behavior without killing momentum.

---

## Tradeoffs

This workflow is not optimized for:

- Maximum speed
- Rapid prototyping
- Demo-driven development

It intentionally trades some velocity for:

- Safety
- Predictability
- Maintainability

---

## When to Adjust

You may want to adapt this workflow if:

- You are working on throwaway prototypes
- You are exploring unknown domains quickly
- You are operating solo with low risk tolerance

Even then, consider preserving:
- Permissioned automation
- Visible execution
- Clear human approval boundaries

---

## Summary

This human workflow emphasizes:

- Explicit control
- Visible execution
- Tiered trust
- Human accountability

AI-assisted development under the AMP Operating Protocol is most effective when automation is **deliberate**, not invisible.
