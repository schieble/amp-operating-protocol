# AMP Operating Protocol — Operating Model

This document defines the **canonical operating model** for using the
AMP Operating Protocol in real software projects.

It describes *how work is intended to flow* between humans and AI agents.
It is descriptive, not prescriptive — adapt deliberately.

---

## Purpose of the Operating Model

The AMP Operating Model exists to:

- Provide a repeatable structure for human–AI collaboration
- Prevent ambiguous ownership between humans and AI
- Reduce rework caused by assumption and invention
- Ensure traceability from intent to implementation

The operating model complements:
- **AGENT_RULES** (what AI may or may not do)
- **Guardrails** (non-negotiable constraints)
- **Prompts** (interfaces for generation)

---

## Core Principles

### 1. Humans Own Intent

Humans are responsible for:
- Defining problems
- Setting goals
- Establishing constraints
- Approving outcomes

AI agents never own intent.

---

### 2. AI Assists Execution

AI agents may:
- Generate structured documents
- Propose task breakdowns
- Suggest code or commands
- Execute approved actions

AI agents do not make final decisions.

---

### 3. Intent Precedes Execution

All meaningful work begins with documented intent.

Execution without documented intent is a failure mode.

---

### 4. Explicit Over Implicit

AMP favors:
- Explicit requirements
- Explicit assumptions
- Explicit approvals

Implicit behavior is treated as risk.

---

## Canonical Workflow

### Step 1: Define the Problem (PRD)

- Create a Product Requirements Document using AMP
- Answer all clarifying questions
- Clearly define:
  - Goals
  - Non-goals
  - Constraints
  - Success criteria

The PRD defines *what* and *why*, never *how*.

---

### Step 2: Pressure Test (Optional but Recommended)

- Submit the PRD to an independent AI reviewer (“Oracle”)
- Request critique, not extension
- Incorporate accepted feedback

This step surfaces blind spots at low cost.

---

### Step 3: Architectural Decisions (ADR)

- Create an ADR when decisions affect:
  - System structure
  - Scalability
  - Long-term maintainability
- Document alternatives and tradeoffs

ADRs preserve reasoning over time.

---

### Step 4: Decompose into Tasks

- Generate tasks from the PRD
- Ensure tasks are:
  - Concrete
  - Ordered
  - Testable
- A task list should be executable by a junior engineer

Tasks define *how work will be done*, not *why it exists*.

---

### Step 5: Implement

- Work occurs in feature branches
- AI agents may propose and execute commands
- High-impact actions (e.g., Git operations) require approval
- Low-risk actions (e.g., tests) may be pre-approved

Permissioned automation balances leverage and safety.

---

### Step 6: Review and Merge

- All changes flow through Pull Requests
- Humans review:
  - Correctness
  - Alignment with intent
  - Test coverage
- CI and guardrails must pass

No direct commits to protected branches.

---

### Step 7: Track Reality

- GitHub Issues and Projects reflect actual state
- No “shadow work” outside the system
- Status reflects reality, not optimism

---

## Session Lifecycle

### Session Start

- Provide relevant context
- State the session goal
- Confirm constraints

### During Session

- Let the AI assist
- Pause before destructive actions
- Resolve ambiguity explicitly

### Session End

- Commit work
- Update handoff or context if needed
- Leave the system in a known-good state

---

## Authority Model

- Humans approve intent and outcomes
- AI proposes actions and artifacts
- Guardrails override convenience

Responsibility cannot be delegated to AI.

---

## When to Slow Down

Slow down when:
- Requirements are unclear
- Architecture is changing
- Scope is expanding
- Multiple systems interact

Speed without clarity creates debt.

---

## Summary

The AMP Operating Model is designed to:

- Maximize AI leverage
- Preserve human accountability
- Reduce rework
- Improve long-term maintainability

Discipline is not overhead.
It is the mechanism that makes AMP work.
