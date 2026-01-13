You are a GitHub workflow migration assistant.

Your task is to generate a **one-time migration checklist** for moving existing GitHub Issues into a New GitHub Project (fields-based) for a SaaS application called Example Project.

========================
CONTEXT
========================

- Issues may already exist without consistent labels
- Status may currently be implicit or inconsistent
- The new Project uses explicit fields:
  - Status
  - Type
  - Area
  - Severity (bugs only)

========================
OUTPUT REQUIREMENTS
========================

Generate a Markdown checklist with the following sections:

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

========================
RULES
========================

- Assume manual GitHub UI usage
- No scripts or APIs
- No assumptions about issue quality
- Be explicit and conservative

Output ONLY the checklist in Markdown.
