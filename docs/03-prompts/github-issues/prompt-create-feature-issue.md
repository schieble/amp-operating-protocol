# Rule: Generating a GitHub Feature Issue

## Goal

To guide an AI assistant in creating a GitHub Feature Request that aligns exactly with the repository's Feature Issue Template. The output should be ready to paste directly into GitHub.

## Output

- **Format:** GitHub Issue (Markdown)
- **Destination:** Paste directly into GitHub Issues
- **Title format:** `[Feature]: <short, clear capability name>`

## Process

1. **Receive Initial Prompt:** The user describes a feature they want to request.
2. **Ask Clarifying Questions:** Ask the questions below to gather all required information.
3. **Generate Issue Content:** Based on the answers, generate the feature request using the structure outlined below.
4. **Present Output:** Provide the final issue content ready for pasting into GitHub.

## Clarifying Questions

Ask the following questions. Do NOT proceed until all are answered.

1. **Problem / Why:**
   - What user or business problem does this feature solve?
   - Who is the primary user?
2. **Scope:**
   - What is explicitly in-scope?
   - What is explicitly out-of-scope?
3. **Acceptance Criteria:** Provide a clear, testable bullet list of conditions for success.
4. **Area:** Choose one: ui / backend / infra / integrations / stt / diarization / auth / billing / docs
5. **Constraints / Non-Functional Requirements:**
   - Latency?
   - Cost?
   - Security?
   - Scale?
   - Compliance?
6. **References:**
   - Related PRDs?
   - Related ADRs?
   - Related GitHub issues?
   - Mocks or diagrams?

## Feature Issue Structure

The generated issue must use EXACTLY this structure and section order:

```
[Feature]: <short, clear capability name>

## Problem / Why
<Problem statement>

## Scope
**In-scope:**
- ...

**Out-of-scope:**
- ...

## Acceptance Criteria
- [ ] ...
- [ ] ...
- [ ] ...

## Area
<ui | backend | infra | integrations | stt | diarization | auth | billing | docs>

## Constraints / Non-Functional Requirements
- Latency:
- Cost:
- Security:
- Scale:
- Compliance:

## References
- PRD:
- ADR:
- Related issues:
- Mocks / diagrams:

## Suggested Labels
feature, <area>
```

## Final Instructions

1. Do NOT create the issue directly — output content only
2. Do NOT invent information or assume answers
3. Output ONLY the final issue content
4. Do NOT add explanations, status tracking, or commentary
5. Do NOT reference this prompt in the output
