# Oracle Review Pattern (Lessons Learned)

This document describes the **Oracle Review Pattern**, a lightweight but
high‑leverage technique discovered through real‑world use of the
AMP Operating Protocol.

The pattern is optional, but strongly recommended for non‑trivial work.

---

## What Is the Oracle Review Pattern?

The Oracle Review Pattern introduces a **second, independent AI reviewer**
after AMP has generated a document such as a PRD, task list, or ADR.

- AMP acts as the **author**
- The Oracle acts as the **reviewer**
- The human remains the **decision maker**

This creates deliberate separation between creation and critique.

---

## Why This Pattern Exists

AMP is optimized for:
- Structure
- Completeness
- Constraint following
- Consistency

However, no single agent should be trusted as both author and reviewer.

The Oracle is used to:
- Challenge assumptions
- Identify missing requirements
- Surface edge cases
- Question scope and tradeoffs
- Spot ambiguity before implementation begins

This mirrors strong human engineering practice.

---

## When to Use the Oracle

The Oracle Review Pattern is especially valuable for:

- Product Requirements Documents (PRDs)
- Task breakdowns that span multiple systems
- Architecture Decision Records (ADRs)
- High‑risk or high‑cost changes
- Work that will be delegated to others

It may be skipped for:
- Trivial changes
- Well‑understood patterns
- Low‑risk refactors

Use judgment.

---

## How the Oracle Is Used

1. AMP generates a document (PRD, tasks, or ADR)
2. The document is treated as *proposed*, not final
3. The document is submitted verbatim to an independent AI
4. The Oracle is instructed to **critique**, not extend

The Oracle should:
- Read the document in full
- Identify gaps, risks, or unclear areas
- Call out assumptions explicitly
- Suggest questions the author failed to ask

The Oracle should **not**:
- Rewrite the document wholesale
- Add new scope automatically
- Make decisions on behalf of the human

---

## Example Oracle Prompt (Conceptual)

While the exact prompt may vary, the intent is consistent:

> “Review this document as if you are responsible for maintaining the system
> long‑term. Identify missing requirements, ambiguous language, risks,
> and questionable assumptions. Do not rewrite unless necessary.”

The goal is pressure testing, not regeneration.

---

## Cost vs Value

In practice, Oracle reviews cost only a few cents
and frequently uncover issues that would otherwise surface later as:

- Rework
- Bugs
- Scope creep
- Architectural debt

The return on investment is consistently positive for complex work.

---

## Handling Oracle Feedback

- Oracle feedback is **advisory**
- Humans decide what to accept or reject
- Accepted feedback should be incorporated deliberately
- Rejected feedback should be consciously rejected, not ignored

Do not blindly merge Oracle output back into AMP.

---

## Common Mistakes

- Treating Oracle feedback as authoritative
- Letting the Oracle expand scope unintentionally
- Skipping Oracle review on complex work “to save time”
- Feeding Oracle output back into AMP without judgment

The Oracle is a reviewer, not a replacement.

---

## Relationship to AMP

The Oracle Review Pattern:
- Does not replace AMP
- Does not weaken guardrails
- Does not automate decisions

It strengthens AMP by adding **independent critique**.

---

## Summary

Think of the pattern this way:

- AMP writes the first draft
- The Oracle challenges it
- The human decides

This simple separation significantly improves quality
without adding heavy process.

---

## Final Note

The Oracle Review Pattern reflects a core AMP belief:

> High‑quality systems emerge from deliberate disagreement,
> not unquestioned confidence.
