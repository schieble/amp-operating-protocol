# AMP Best Practices

**Purpose:** Document effective patterns for working with AMP on complex software projects.  
**Audience:** Teams adopting the AMP Operating Protocol for production development.  
**Last Updated:** 2026-01-11

---

## 1. Context Management

AMP has limited context windows. Plan for it.

### 1.1 Handoff Documents

Create handoff documents at session boundaries to preserve state.

**Naming Convention:**
- `CURRENT-HANDOFF-{YYYY-MM-DD}-{HHMM}.md` — Active (only one)
- `ARCHIVED-HANDOFF-{YYYY-MM-DD}-{session}.md` — Previous sessions

**Handoff Content:**
- Session summary (what was done)
- Current state (branch, test status, blockers)
- Next steps (prioritized, actionable)
- Key files reference
- Quick start commands

**When to Create:**
- Before ending a session
- Before context fills up (~70% capacity)
- At logical milestone completion

### 1.2 Attach Key Files

Start sessions by attaching:
- `CONTEXT.md` — Project state and conventions
- `AGENT_RULES.md` — Behavioral guardrails
- Current handoff document
- Relevant PRD/task file

### 1.3 Small, Focused Tasks

- One logical task per session when possible
- Break large features into phases
- Complete and commit before moving on

---

## 2. Project Documentation

### 2.1 PRD Structure

PRDs should be structured for use with AI tools:

```markdown
# Feature Name PRD

## Problem Statement
[2-3 sentences]

## Requirements
### Functional
- FR-1: [Requirement]
- FR-2: [Requirement]

### Non-Functional
- NFR-1: [Requirement]

## Technical Approach
[High-level architecture]

## Out of Scope
[Explicit boundaries]

## Success Criteria
[How to verify completion]
```

**Key Practices:**
- Number requirements (FR-1, FR-2) for reference
- Keep under 500 lines
- Include "Out of Scope" to prevent drift

### 2.2 Task File Structure

Break PRDs into executable tasks:

```markdown
# Feature Tasks

## Phase 1: Foundation
### Task 1.0: [Name]
- **Files:** [specific paths]
- **Acceptance:** [testable criteria]
- **Dependencies:** [prior tasks]

### Task 1.1: [Name]
...
```

**Key Practices:**
- One task = one commit (roughly)
- Include file paths AMP should modify
- Define acceptance criteria upfront
- Group related tasks into phases

### 2.3 Context File

Maintain a `CONTEXT.md` with:
- Tech stack summary
- Locked-in decisions
- Current focus
- Naming conventions
- Open decisions

Update at session end, not during.

---

## 3. Git Workflow Integration

### 3.1 Branch-Based Development

- All work in feature branches
- Never commit directly to `main` or `dev`
- Small, reviewable commits

### 3.2 Guardrails Document

Create `AMP_WORKFLOW_GUARDRAILS.md` defining:
- Branch naming conventions
- Protected branches
- PR requirements
- What AMP can/cannot do (e.g., cannot merge PRs)

### 3.3 Session Acknowledgment

Require AMP to acknowledge rules at session start:

> "I have read and will follow:
> - AMP_WORKFLOW_GUARDRAILS.md
> - AGENT_RULES.md"

---

## 4. Testing Practices

### 4.1 Test-First for Complex Logic

- Write tests before implementation for core business logic
- AMP can generate comprehensive test cases
- Use existing test patterns as templates

### 4.2 Run Tests Frequently

- After each significant change
- Before committing
- Include test commands in handoffs

### 4.3 Manual Test Plans

For features requiring manual testing:
- Document test scenarios
- Include expected outcomes
- AMP can help analyze logs/output

---

## 5. Session Patterns

### 5.1 Session Start

1. Attach context files (CONTEXT.md, AGENT_RULES.md)
2. Attach current handoff
3. State the goal for this session
4. Let AMP review and confirm understanding

### 5.2 Mid-Session Checkpoints

When context fills:
1. Commit current work
2. Create handoff document
3. Push branch
4. End session gracefully

### 5.3 Session End

1. Commit and push
2. Create/update handoff
3. Update CONTEXT.md if decisions changed
4. Archive old handoff, create new CURRENT-*

---

## 6. Communication Patterns

### 6.1 Be Specific

❌ "Fix the auth"  
✅ "Fix the JWT validation in src/lib/auth/jwt.ts - tokens are rejected after 1 hour"

### 6.2 Ask for Opinions

AMP has good judgment. Use it:
- "What's your opinion on the approach?"
- "Should we consult the Oracle?"
- "What order should we tackle these?"

### 6.3 Confirm Before Destructive Actions

AMP should pause and confirm before:
- Deleting files
- Major refactors
- Dependency changes
- Git operations on protected branches

---

## 7. Debugging with AMP

### 7.1 Provide Context

- Error messages (full, not truncated)
- Relevant log output
- What you expected vs. what happened
- What you've already tried

### 7.2 Use the Oracle

For complex debugging across multiple files:
- AMP can consult the Oracle for analysis
- Provide file paths and context
- Oracle excels at finding root causes

### 7.3 Iterative Narrowing

1. Reproduce the issue
2. Add logging/assertions
3. Narrow to specific file/function
4. Fix and verify

---

## 8. Known AMP Limitations

### 8.1 Context Window

- Plan for ~128k token limit
- Create handoffs before hitting limit
- Break large tasks into sessions

### 8.2 No Persistent Memory

- AMP doesn't remember previous sessions
- Handoff documents bridge sessions
- Attach relevant context every time

### 8.3 Cannot Execute Long-Running Processes

- No background processes
- No interactive prompts
- User must run servers, watch commands

### 8.4 Cannot Merge PRs

- AMP creates PRs, humans merge
- Maintains review accountability

---

## 9. Anti-Patterns to Avoid

| Anti-Pattern | Why It Fails | Better Approach |
|--------------|--------------|-----------------|
| Massive single-session features | Context overflow | Phase into smaller tasks |
| No handoff documents | Lost context | Always create handoffs |
| Vague requirements | Scope creep, wrong implementation | Numbered FRs with acceptance criteria |
| Skipping tests | Regressions | Test alongside implementation |
| Direct commits to main | No review, breaks CI | Feature branches + PRs |
| Not attaching context | AMP lacks project knowledge | Attach CONTEXT.md every session |

---

## 10. Evolving This Document

This is a living document. Update when:
- New patterns prove effective
- Pain points are solved
- AMP capabilities change

Track what works, discard what doesn't.
