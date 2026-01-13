# AMP Operating Protocol — Common Failure Modes

The AMP Operating Protocol is designed to be disciplined and safe. When it fails, it usually fails in
predictable ways. This document lists common failure modes, why they happen,
and how to prevent them.

Use this as a quick diagnostic when work starts to feel chaotic or low-quality.

---

## 1) Skipping Clarifying Questions

**Symptoms**
- PRDs feel “reasonable” but miss critical constraints
- Tasks are incomplete or mis-ordered
- Rework appears late during implementation

**Why it happens**
- Humans want speed and treat questions as friction
- The AI fills gaps with implicit assumptions

**Prevention**
- Always answer the clarifying questions for PRDs/tasks/ADRs
- If something is unknown, explicitly mark it as **TBD** or **unknown**
- Require a “review pass” before treating an artifact as final

---

## 2) Letting the AI Invent Requirements (“Hallucination”)

**Symptoms**
- Requirements appear that nobody asked for
- “Nice-to-have” features sneak into scope
- Confident language masks uncertainty

**Why it happens**
- The AI optimizes for completeness
- Humans reward confident output

**Prevention**
- Treat AI output as a **proposal**
- Require explicit assumptions to be listed
- Reject invented requirements and tighten the prompt/rules

---

## 3) Treating AMP Like a Code Generator

**Symptoms**
- Large code dumps are produced and merged with minimal review
- Architecture becomes inconsistent
- Bugs increase and maintainability declines

**Why it happens**
- It feels efficient in the moment
- Review becomes superficial when output volume is high

**Prevention**
- Use AI tools primarily for planning, decomposition, and critique
- Keep code changes reviewable and incremental
- Require tests and explainability for non-trivial changes

---

## 4) Bypassing Guardrails for Speed

**Symptoms**
- “Temporary” shortcuts become permanent
- Protected branches get modified improperly
- CI gates are treated as optional

**Why it happens**
- Pressure to ship
- Overconfidence in AI output

**Prevention**
- Treat guardrails as load-bearing
- If guardrails feel too strict, revise them intentionally
- Never bypass guardrails silently

---

## 5) Allowing Unbounded Autonomy

**Symptoms**
- The AI starts “driving” without explicit approval
- Commands run that the human did not intend
- The project diverges from goals

**Why it happens**
- Convenience and momentum
- Poorly defined permission model

**Prevention**
- Use **permissioned automation**
- Require approval for high-impact actions (Git, deploy, deletes)
- Pre-approve low-risk repetitive actions (tests, lint) to reduce noise

---

## 6) Working Without a Stable Operating Context

**Symptoms**
- The AI repeats questions or forgets constraints
- Output changes in tone or assumptions across sessions
- Inconsistent architectural recommendations

**Why it happens**
- Missing or outdated context documents
- Sessions become too long or too broad

**Prevention**
- Maintain a lightweight, current context document
- Keep sessions goal-focused and time-bounded
- End sessions with a short handoff when work is mid-stream

---

## 7) Confusing Intent Documents with Execution Plans

**Symptoms**
- PRDs include implementation details and code-level decisions
- Tasks read like strategy documents
- ADRs get written after code is already merged

**Why it happens**
- Blurred separation between “what/why” and “how”
- Rushing to implementation

**Prevention**
- Enforce **Intent vs Execution**
- PRDs: what/why, scope, success
- ADRs: decisions + tradeoffs
- Tasks: executable steps

---

## 8) Overloading the System with Too Much Process

**Symptoms**
- Documentation becomes performative
- People stop reading the rules
- Work slows down without increasing quality

**Why it happens**
- Adding rules to compensate for lack of judgment
- Confusing “more process” with “more safety”

**Prevention**
- Keep the core small and stable
- Add workflows only when there is repeated evidence
- Prefer clarity over volume

---

## 9) Under-Specifying “Done”

**Symptoms**
- Features ship without clear acceptance criteria
- Testing is inconsistent
- PRDs can’t be validated

**Why it happens**
- Success criteria are vague
- Teams optimize for shipping, not correctness

**Prevention**
- Require explicit success metrics in PRDs
- Require acceptance criteria for user-facing work
- Require tests to reflect the intended behavior

---

## 10) Failing to Update After Learning

**Symptoms**
- Same mistakes repeat
- Workarounds become folklore
- Protocol slowly drifts

**Why it happens**
- Lessons learned aren’t captured
- Improvements stay in someone’s head

**Prevention**
- Capture lessons learned as optional workflows
- Version changes to rules/prompts
- Review failure modes periodically

---

## Quick Self-Check

If things feel off, ask:

1. Did we answer clarifying questions?
2. Are assumptions explicit?
3. Are guardrails being followed?
4. Do we have clear intent (PRD/ADR) before code?
5. Are we using permissioned automation correctly?
6. Are we keeping changes small and reviewable?

---

## Summary

The AMP Operating Protocol succeeds when:
- Humans stay engaged
- Intent is explicit
- Guardrails are respected
- AI output is reviewed as proposals

Most failures come from trading discipline for speed.
