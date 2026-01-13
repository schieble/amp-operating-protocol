# Rule: Generating a Monthly GitHub Project Health Check

## Goal

To guide an AI assistant in creating a repeatable monthly audit checklist for a GitHub Project managing work for a SaaS product.

## Output

- **Format:** Markdown checklist
- **Purpose:** Monthly audit designed to be completed in under 15 minutes
- **Audience:** Solo founder or small team

## Audit Goals

Ensure that:

- The Project reflects reality
- Bugs are triaged correctly
- No work is happening outside the system
- Status drift is caught early
- Technical debt is visible

## Checklist Structure

Generate a Markdown checklist with the following sections:

```
## Project Hygiene
Checks for stale issues, incorrect statuses, and missing fields.

## Bug Health
Checks focused on:
- sev1 / sev2 aging
- untriaged bugs
- blocked bugs

## Work In Progress (WIP)
Checks for:
- Too many in-progress items
- Long-running issues
- Orphaned PRs

## Documentation Alignment
Checks that:
- Active Epics have PRDs
- Architectural changes have ADRs
- Links between docs and issues exist

## Action Items
A short list of corrective actions to take if problems are found.
```

## Final Instructions

1. Checklist format only — no explanations or commentary
2. Designed to be completed in under 15 minutes
3. Suitable for solo founder or small team
4. Output ONLY the Markdown
