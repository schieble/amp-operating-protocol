# Rule: Generating an Architecture Decision Record (ADR)

## Goal

To guide an AI assistant in creating a complete Architecture Decision Record (ADR) in Markdown format. The ADR should document a significant architectural decision, including context, alternatives considered, and consequences.

## Output

- **Format:** Markdown (`.md`)
- **Location:** `docs/adr/`
- **Filename:** `adr-XXXX-[decision-title].md` (kebab-case, using the next available ADR number)

## Process

1. **Receive Initial Prompt:** The user provides a brief description of an architectural decision.
2. **Ask Clarifying Questions:** Before writing the ADR, ask the clarifying questions below to gather sufficient context.
3. **Generate ADR:** Based on the user's answers, generate an ADR using the structure outlined below.
4. **Save ADR:** Save the document using the naming convention above.

## Clarifying Questions

Ask the following questions, grouped and numbered clearly:

### A. Decision Summary

1. What is the architectural decision being made?
2. Is this decision new, or formalizing an existing choice?
3. What part of the system does this affect? (e.g., ingestion, API, UI, infrastructure)

### B. Context & Drivers

4. What problem or constraint led to this decision?
5. What requirements are driving it? (latency, cost, reliability, MVP speed, enterprise readiness)
6. Is this for MVP only, or intended to be long-term?

### C. Alternatives

7. What alternatives were seriously considered?
8. Why was each alternative rejected?
9. Were any options partially adopted or deferred?

### D. Consequences

10. What are the positive outcomes of this decision?
11. What are the negative tradeoffs or risks?
12. Does this introduce vendor lock-in or future migration work?

### E. Status & References

13. What is the status? (Proposed / Accepted / Deprecated / Superseded)
14. Are there related PRDs, GitHub issues, or diagrams to reference?

## ADR Structure

The generated ADR should include the following sections:

```
# ADR-XXXX: <Short Decision Title>

## Status

## Date

## Context

## Decision

## Alternatives Considered

## Consequences

## Open Questions

## References
```

## Final Instructions

1. Do NOT invent decisions or assume answers
2. Ask clarifying questions until you have enough information
3. Keep the ADR concise, factual, and implementation-aware
4. Output ONLY the final Markdown — no commentary or explanations
5. This is an architectural record, not a PRD or task list
