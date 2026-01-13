# Rule: Setting Up a GitHub Project Workflow

## Goal

To guide an AI assistant in creating a precise, step-by-step checklist for setting up a New GitHub Project (fields-based) via the GitHub UI.

## Output

- **Format:** Markdown checklist with headings and checkboxes
- **Purpose:** Professional internal runbook for manual project setup
- **Audience:** Developer or project maintainer

## Context

This project must support:

- Bugs, features, tech debt, and spikes
- Severity-based bug triage
- Area/component visibility
- Clean integration with GitHub Issues and PRs

## Process

1. **Clarify (Ask Only If Needed):** Ask the following questions ONLY if answers are not obvious:
   - Should this be an Organization-level project or Repository-level project?
   - Should this project include multiple repositories or only one?
   - Should automation rules be enabled immediately or added later?
   - Should priority be tracked explicitly (P0–P3), or inferred informally?

2. **Generate Setup Checklist:** Once clarified, generate the checklist using the structure below.

## Checklist Structure

Generate a numbered checklist with the following sections:

```
### A. Project Creation
- Exact project name
- Where to create it (org vs repo)
- Visibility settings

### B. Required Fields
For each field:
- Field name
- Field type (single select, text, number, etc.)
- Allowed values (in order)
- Whether it is required or optional

Fields MUST include: Status, Type, Severity, Area, Priority (if enabled)

### C. Views
For each view:
- View name
- View type (Board / Table)
- Grouping
- Filters
- Sort order
- Intended usage (one short sentence)

Views MUST include: Active Work board, Bug Triage table, Backlog table, Area/Component view

### D. Automation Rules
For each automation:
- Trigger
- Action
- Exact field/value changes

Only include automations supported by GitHub Projects.

### E. Issue Integration
Checklist for:
- Adding issues to the project
- Default field values for new issues
- How PRs affect issue status

### F. Verification Checklist
Confirm:
- Issues move correctly across statuses
- Bugs can be filtered by severity
- Features and bugs coexist cleanly
- The project reflects reality without manual duplication
```

## Final Instructions

1. Be explicit about field names, field types, options, and ordering
2. Do NOT invent GitHub features or automation that does not exist
3. Do NOT include opinions or explanations unless they affect setup correctness
4. Output ONLY the final checklist
5. Do NOT restate the prompt
