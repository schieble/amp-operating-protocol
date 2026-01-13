# Rule: Generating a GitHub Issues Migration Checklist

## Goal

To guide an AI assistant in creating a one-time migration checklist for moving existing GitHub Issues into a New GitHub Project (fields-based).

## Output

- **Format:** Markdown checklist
- **Purpose:** Step-by-step guide for manual migration via GitHub UI
- **Audience:** Developer or project maintainer

## Context

- Issues may already exist without consistent labels
- Status may currently be implicit or inconsistent
- The new Project uses explicit fields:
  - Status
  - Type
  - Area
  - Severity (bugs only)

## Checklist Structure

Generate a Markdown checklist with the following sections:

```
## Pre-Migration Prep
Steps to complete BEFORE touching any issues.

## Issue Audit
Checklist for reviewing each existing issue:
- Type assignment
- Area assignment
- Severity (if bug)
- Close or keep decision

## Bulk Migration Steps
Safe steps to add issues to the Project without losing information.

## Status Normalization
Rules for mapping current reality into:
- Inbox
- Triage
- Ready
- In Progress
- In Review
- Done

## Post-Migration Verification
Checks to confirm the Project reflects reality.
```

## Final Instructions

1. Assume manual GitHub UI usage — no scripts or APIs
2. No assumptions about issue quality
3. Be explicit and conservative
4. Output ONLY the checklist in Markdown
