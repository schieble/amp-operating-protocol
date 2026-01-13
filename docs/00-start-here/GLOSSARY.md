# AMP Operating Protocol — Glossary

This glossary defines key terms as they are used within the **AMP Operating Protocol**.
The intent is to create shared language and reduce ambiguity for both humans and AI agents.

If a term is used in documentation and is not listed here, it should be added.

---

## AMP (AI Management Protocol)

A disciplined operating protocol for human–AI collaboration in software development.
AMP defines rules, workflows, and constraints that govern how AI agents assist humans
without replacing judgment or accountability.

AMP is tool-agnostic and documentation-first.

---

## Operating Protocol

A formalized set of rules, invariants, and interaction patterns that define how
participants (human and AI) are expected to behave.

Unlike an operating model, a protocol emphasizes explicit contracts and constraints.

---

## Agent

An AI system operating under explicit constraints defined by AMP.
An agent may generate documents, propose code, or execute commands only within
approved boundaries.

Agents do not own outcomes.

---

## Human-in-the-Loop

A design principle where humans retain decision authority and accountability.
AI agents may propose actions, but humans approve, reject, or modify them.

AMP intentionally prevents fully autonomous operation.

---

## AGENT_RULES

The authoritative behavioral contract governing AI agent behavior.
AGENT_RULES define what an agent may and may not do.

If any other document conflicts with AGENT_RULES, AGENT_RULES take precedence.

---

## Guardrails

Non-negotiable workflow and safety constraints.
Guardrails typically cover:
- Git and branch protection
- Approval requirements
- Destructive actions
- CI and testing requirements

Guardrails prioritize safety over speed.

---

## Intent vs Execution

A core AMP principle.

- **Intent** describes *what* and *why* (PRDs, ADRs, task plans)
- **Execution** describes *how* (code changes)

Intent is documented before execution begins.

---

## PRD (Product Requirements Document)

A document that defines:
- The problem being solved
- Goals and success criteria
- Functional requirements
- Non-goals and scope boundaries

PRDs describe intent, not implementation.

---

## ADR (Architecture Decision Record)

A document that captures a significant architectural decision.
An ADR records:
- Context
- Decision
- Alternatives considered
- Tradeoffs and consequences

ADRs exist to preserve reasoning over time.

---

## Tasks / Task List

A step-by-step, executable plan derived from a PRD.
Tasks are concrete, ordered, and testable.

A task list should guide a junior developer without requiring interpretation.

---

## Oracle

An independent AI reviewer used to critique documents produced with AMP.
The Oracle:
- Does not generate new work
- Challenges assumptions
- Identifies gaps and risks

The Oracle pattern provides low-cost pressure testing.

---

## Clarifying Questions

Mandatory questions asked by an AI agent before generating output.
Clarifying questions exist to:
- Prevent assumption
- Reduce ambiguity
- Surface missing constraints

Skipping clarifying questions is a common failure mode.

---

## Invention (Hallucination)

The act of fabricating requirements, facts, or decisions not explicitly provided.
AMP explicitly forbids invention.

When information is unknown, it should be marked as unknown or TBD.

---

## Permissioned Automation

A trust model where AI agents may execute certain actions only after human approval.
High-impact actions (e.g., Git operations) require explicit permission.

Low-risk actions (e.g., running tests) may be pre-approved.

---

## Feature Branch

A short-lived Git branch used to implement a specific change.
All work under AMP occurs in feature branches.

Direct commits to protected branches are forbidden.

---

## Pull Request (PR)

A formal request to merge changes into a protected branch.
PRs provide:
- Reviewability
- Traceability
- Accountability

All merges occur via PRs.

---

## Protected Branch

A branch (e.g., `main`, `dev`) that cannot be modified directly.
Protected branches enforce:
- PR usage
- CI requirements
- Review gates

---

## GitHub Project

A structured project board used to track work state explicitly.
GitHub Projects reflect reality and replace informal status tracking.

---

## Inbox / Triage / Ready / In Progress / In Review / Done

Explicit work states used in AMP-aligned GitHub Projects.

These states represent actual work status, not intention.

---

## Session

A bounded period of work with an AI agent.
Sessions have:
- A defined goal
- Clear start and end
- Explicit context

Long-running sessions are avoided to prevent context drift.

---

## Context

The minimal set of information required for an AI agent to operate correctly.
Context typically includes:
- Tech stack
- Constraints
- Current focus
- Active decisions

Context must be provided explicitly.

---

## Handoff

A document capturing the state of work at the end of a session.
Handoffs preserve continuity across sessions.

---

## Failure Mode

A predictable way in which AMP breaks down when misused.
Failure modes are documented to prevent repeated mistakes.

---

## Tool-Agnostic

A design principle where AMP does not depend on a specific AI tool or editor.
AMP may be used with AMP, Cursor, Copilot, or other systems.

Only the protocol matters.

---

## Discipline

The intentional tradeoff of speed for correctness, safety, and maintainability.
Discipline is a core feature of AMP, not a side effect.

---

## Accountability

The principle that humans remain responsible for outcomes, regardless of AI assistance.
AMP explicitly prevents responsibility from being delegated to AI.

---

## Drift

Unintentional deviation from core rules and constraints over time.
Drift often occurs when guardrails are bypassed “temporarily.”

AMP evolution is designed to minimize drift.

---

## Versioning

The practice of tracking meaningful changes to rules, workflows, and prompts.
AMP uses semantic versioning to signal stability and breaking changes.

---

## Final Note

Shared language is critical for safe human–AI collaboration.
If a term is unclear, ambiguous, or overloaded, add it here.
