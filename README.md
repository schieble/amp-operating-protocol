# AMP Operating Protocol

**AMP Operating Protocol** is a disciplined, tool-agnostic operating protocol for working
with AI development tools on real software projects without sacrificing correctness,
safety, or human accountability.

This is a **documentation-only repository**. It defines the rules, workflows, and prompts
needed to use AI tools as constrained engineering partners — not as autonomous code generators.

This repository does **not** document the AMP tool itself. It documents the operating protocol
developed through real-world usage of AI-assisted software development tools.

---

## What the AMP Operating Protocol Is

The AMP Operating Protocol is:
- A **tool-agnostic operating protocol**, not software
- A set of explicit rules and invariants for human–AI collaboration
- A way to use AI development tools without losing control
- Applicable to AMP, Cursor, Copilot, and similar systems

The protocol assumes:
- Humans decide *what* and *why*
- AI tools assist with *how*
- Humans remain accountable for outcomes

---

## What the AMP Operating Protocol Is Not

The AMP Operating Protocol is not:
- An AI tool or SDK
- A code generator
- A replacement for engineering judgment
- A vendor-specific workflow

Individual AI tools (including AMP itself) **may** generate code.
The protocol governs *how those tools are used*.

If speed at all costs is your goal, this protocol will feel restrictive.
That is intentional.

---

## Repository Structure

```txt
AGENTS.md              Orientation for AI tools interacting with this repository

docs/
  00-start-here/     Entry point, adoption guidance, failure modes
  01-core/           Non-negotiable rules and guardrails
  02-workflows/      How work flows in practice
  03-prompts/        Copy/paste prompts for AI agents
  90-examples/       Non-proprietary examples only
```

If there is any conflict, `docs/01-core/` is authoritative.

Start with:
1. `docs/00-start-here/AMP_OPERATING_MODEL.md`
2. `docs/00-start-here/WHO_AMP_IS_FOR.md`
3. `docs/00-start-here/COMMON_FAILURE_MODES.md`

---

## How the AMP Operating Protocol Is Used

Typical flow:
1. Write a PRD using the protocol
2. (Optional) Review with an independent AI reviewer (“Oracle”)
3. Generate tasks from the PRD
4. Implement via feature branches and Pull Requests
5. Track work explicitly in GitHub Projects

The protocol is designed to be adapted.
Change the rules first — not the behavior.

---

## Versioning

This repository follows semantic versioning.

- **v1.0.0** — Initial stable release of the AMP Operating Protocol
- Future releases may add workflows or prompts
- Core invariants change rarely and deliberately

---

## License

AMP Operating Protocol is released under the MIT License.

You are free to use, modify, and distribute this protocol,
including for commercial purposes.

See `LICENSE` for details.

---

## Final Note

The AMP Operating Protocol works best when AI tools are treated as:

> Junior engineers with perfect memory, high speed, and no intuition.

You would not let such an engineer guess requirements,
skip reviews, or merge to main.

The protocol enforces the same discipline.
