# Evolving AMP Operating Protocol

AMP Operating Protocol is designed to evolve.
However, it must evolve **deliberately** to avoid drift, loss of safety,
or erosion of its core principles.

This document defines how to evolve AMP responsibly over time.

---

## Why Evolution Needs Rules

AMP is a protocol, not a static artifact.

Without explicit evolution rules:
- Guardrails get bypassed “temporarily”
- Prompts drift silently
- Accountability weakens
- The system becomes inconsistent

Evolution without discipline is a failure mode.

---

## What Is Considered Stable

The following are **core invariants** and should change rarely:

- Humans own intent and outcomes
- AI assists, but does not decide
- Clarifying questions are mandatory
- Invention (hallucination) is forbidden
- Intent precedes execution
- High-impact actions require approval

If these change, AMP itself has changed.

---

## What Is Safe to Customize

You are expected to customize AMP to your context.

Safe areas for customization include:
- Branching strategies
- Testing depth and tooling
- Prompt phrasing (while preserving constraints)
- Folder structure
- Review thresholds
- CI requirements

Customization should reflect reality, not preference.

---

## Dimensions of Change

AMP evolves along three primary dimensions:

1. **Rules**  
   Behavioral constraints and guardrails

2. **Workflows**  
   How work flows from intent to execution

3. **Prompts**  
   Interfaces used to interact with AI agents

Change **one dimension at a time**.

Avoid simultaneous changes across dimensions.

---

## How to Make Changes Safely

When evolving AMP:

1. Identify the problem clearly
2. Change the smallest thing that could help
3. Document the change and the rationale
4. Observe outcomes over real usage
5. Keep or revert based on evidence

Avoid speculative changes.

---

## Prompt Evolution Guidelines

Prompts are interfaces.

When modifying prompts:
- Preserve clarifying-question gates
- Preserve “do not invent” language
- Keep output structure stable
- Update assumptions explicitly
- Version meaningful changes

Breaking a prompt silently creates downstream confusion.

---

## Detecting Drift

Common signs of unhealthy drift:
- AI output becomes inconsistent
- Guardrails are bypassed informally
- Humans stop reviewing outputs carefully
- Rules are overridden for convenience
- Lessons learned are not captured

When drift appears:
Pause.
Re-anchor to core invariants.

---

## Versioning Strategy

AMP uses semantic versioning:

- **MAJOR**: Breaking changes to core invariants
- **MINOR**: New workflows or prompts
- **PATCH**: Clarifications and non-breaking fixes

Version numbers communicate stability expectations.

---

## Capturing Lessons Learned

Not every improvement belongs in core rules.

Use:
- Optional workflows
- Lessons learned documents
- Advisory guidance

Only promote patterns to core after repeated validation.

---

## When to Slow Evolution

Slow down changes when:
- Multiple teams rely on AMP
- High-risk systems are involved
- Changes affect guardrails or authority boundaries

Stability is a feature.

---

## Summary

AMP should evolve:
- Intentionally
- Transparently
- Incrementally

Discipline in evolution preserves trust.

The goal is not novelty — it is reliability.
