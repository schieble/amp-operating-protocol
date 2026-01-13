# Rule: Generating a GitHub Bug Issue

## Goal

To guide an AI assistant in creating a GitHub Bug Report that aligns exactly with the repository's Bug Issue Template. The output should be ready to paste directly into GitHub.

## Output

- **Format:** GitHub Issue (Markdown)
- **Destination:** Paste directly into GitHub Issues
- **Title format:** `[Bug]: <short, specific summary>`

## Process

1. **Receive Initial Prompt:** The user describes a bug they've encountered.
2. **Ask Clarifying Questions:** Ask the questions below to gather all required information.
3. **Generate Issue Content:** Based on the answers, generate the bug report using the structure outlined below.
4. **Present Output:** Provide the final issue content ready for pasting into GitHub.

## Clarifying Questions

Ask the following questions. Do NOT proceed until all are answered.

1. **Summary:** In one sentence, what is broken?
2. **Severity:** Choose one: sev1 / sev2 / sev3
3. **Area:** Choose one: ui / backend / infra / integrations / stt / diarization / auth / billing / docs
4. **Steps to Reproduce:** Provide exact, numbered steps.
5. **Expected Behavior:** What should have happened?
6. **Actual Behavior:** What actually happened?
7. **Environment:**
   - Env: local / dev / staging / prod
   - Browser / OS (if applicable)
   - Commit or branch (if known)
   - User role or account context (if relevant)
8. **Logs / Screenshots:** Any logs, error messages, screenshots, or videos? (If none, answer "None")
9. **Verification:**
   - Can you reproduce this reliably? (yes/no)
   - Is this a regression? (yes/no)
   - Have you confirmed logs/screenshots contain no secrets? (yes/no)

## Bug Issue Structure

The generated issue must use EXACTLY this structure and section order:

```
[Bug]: <short, specific summary>

## Summary
<Summary text>

## Severity
<sev1 | sev2 | sev3>

## Area
<ui | backend | infra | integrations | stt | diarization | auth | billing | docs>

## Steps to Reproduce
1.
2.
3.

## Expected Behavior
<Expected behavior>

## Actual Behavior
<Actual behavior>

## Environment
- Env:
- Browser / OS:
- Commit / Branch:
- User / Role:

## Logs / Screenshots
<paste logs here, or "None">

## Verification
- Reproducible: <yes/no>
- Regression: <yes/no>
- Logs sanitized: <yes/no>

## Suggested Labels
bug, <severity>, <area>
```

## Final Instructions

1. Do NOT create the issue directly — output content only
2. Do NOT invent information or assume answers
3. Output ONLY the final issue content
4. Do NOT add explanations, checklists, or commentary
5. Do NOT reference this prompt in the output
