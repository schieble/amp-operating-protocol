# Rule: Generating a GitHub Project README

## Goal

To guide an AI assistant in creating a concise Project README or description for a GitHub Project (fields-based). The README should explain how the project is used to manage work.

## Output

- **Format:** Markdown
- **Destination:** GitHub Project description field or linked Markdown document
- **Length:** Under ~1 page

## Context

The project follows these principles:

- GitHub Issues are the unit of work
- Status is tracked ONLY in the Project
- Markdown files (PRDs, ADRs) describe intent, not execution
- PRs close Issues
- CodeRabbit is used for automated review

## README Structure

Generate a Markdown document with the following sections:

```
## Project Purpose
Explain what this Project is for and what it is NOT for.

## What Belongs Here
Bullet list of allowed work items.

## What Does NOT Belong Here
Bullet list of anti-patterns.

## Status Definitions
Short explanation of each status column:
- Inbox
- Triage
- Ready
- In Progress
- In Review
- Done

## Rules of Use
Clear, enforceable rules (e.g., "Every PR must close an issue").
```

## Final Instructions

1. Keep it under ~1 page
2. Use direct, operational language
3. No opinions or philosophy
4. No references to tools not already in use
5. Do NOT include setup instructions
6. Output ONLY the final Markdown
