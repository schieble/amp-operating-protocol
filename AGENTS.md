# AGENTS.md

This file provides orientation and constraints for AI agents
interacting with the AMP Operating Protocol repository.

It is informational, not authoritative.
If there is any conflict, follow the documentation in `docs/01-core/`.

---

## Repository Purpose

This repository contains the **AMP Operating Protocol**:
rules, workflows, and prompts for disciplined human–AI collaboration
in software development.

It is documentation-only.
There is no application code in this repository.

---

## Repository Structure

- `docs/00-start-here/` — Entry point and adoption guidance
- `docs/01-core/` — Non-negotiable rules and guardrails
- `docs/02-workflows/` — How work flows in practice
- `docs/03-prompts/` — Copy/paste prompts for AI agents
- `docs/90-examples/` — Non-proprietary examples only

Directory numbers indicate **authority and stability**, not order of execution.

---

## Conventions

- All documentation is Markdown
- Documentation files use `UPPER_SNAKE_CASE.md`
- Prompt files use `lowercase-kebab-case.md`
- Prompt files are prefixed with `prompt-`
- Examples must remain generic
  - Use **"Example Project"** as the placeholder name

---

## Commands

There are no build, test, or runtime commands.
Do not attempt to run or execute anything in this repository.

---

## Constraints

AI agents must not:
- Introduce real project names or internal references
- Add secrets, tokens, or credentials
- Treat prompts as executable instructions
- Modify core rules without explicit human approval

All changes should preserve:
- Tool-agnosticism
- Human accountability
- Intent-before-execution discipline

---

## Final Note

This repository is a protocol, not a product.
Clarity and correctness are prioritized over speed or automation.
