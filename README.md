# AMP Operating Protocol

**AMP (AI Management Protocol)** is a disciplined operating protocol for working
with AI agents on real software projects without sacrificing correctness,
safety, or human accountability.

This repository defines the rules, workflows, and prompts needed to treat AI
as a constrained engineering partner — not a code generator.

---

## What AMP Is

AMP is:
- A **protocol**, not a tool or SDK
- A set of explicit rules and invariants for human–AI collaboration
- A way to get leverage from AI without losing control
- Tool-agnostic (AMP, Cursor, Copilot, etc.)

AMP assumes:
- Humans decide *what* and *why*
- AI assists with *how*
- Humans remain accountable for outcomes

---

## What AMP Is Not

AMP is not:
- A code generator
- A shortcut around thinking
- A replacement for engineering judgment
- A vendor-specific workflow

If speed at all costs is your goal, AMP will feel restrictive.
That is intentional.

---

## Repository Structure

```txt
AGENTS.md              Orientation for AI agents working in this repo

docs/
  00-start-here/     Entry point, adoption guidance, failure modes
  01-core/           Non-negotiable rules and guardrails
  02-workflows/      How work flows in practice
  03-prompts/        Copy/paste prompts for AI agents
  90-examples/       Non-proprietary examples only
```

Start with:
1. `docs/00-start-here/WHO_AMP_IS_FOR.md`
2. `docs/00-start-here/COMMON_FAILURE_MODES.md`
3. `docs/00-start-here/AMP_OPERATING_MODEL.md`

---

## How AMP Is Used

Typical flow:
1. Write a PRD with AMP
2. (Optional) Review with an independent AI reviewer (“Oracle”)
3. Generate tasks from the PRD
4. Implement via feature branches and Pull Requests
5. Track work explicitly in GitHub Projects

AMP is designed to be adapted.
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

You are free to use, modify, and distribute this framework,
including for commercial purposes.

See `LICENSE` for details.

---

## Final Note

AMP works best when treated as:

> A junior engineer with perfect memory, high speed, and no intuition.

You would not let that engineer guess requirements,
skip reviews, or merge to main.

AMP follows the same rules.
