# AMP Operating Protocol — v1.0 Release Checklist

This checklist defines the minimum bar for publishing a stable AMP Operating Protocol release.
It is intentionally explicit to prevent accidental omissions.

Complete all items before tagging `v1.0.0`.

---

## 1. Repository Structure

- [ ] Canonical directory structure implemented
- [ ] No project-specific or proprietary files included
- [ ] All documentation placed under `docs/`
- [ ] Clear separation between:
  - Core rules
  - Workflows
  - Prompts
  - Lessons learned
- [ ] Examples contain no sensitive or private information

---

## 2. Core Authority & Rules

- [ ] `AGENT_RULES.md` exists and is clearly marked as authoritative
- [ ] Rule precedence is unambiguous
- [ ] Guardrails are documented and referenced
- [ ] No conflicting rules across documents
- [ ] Best practices are labeled as advisory, not mandatory

---

## 3. Operating Model Completeness

- [ ] `AMP_OPERATING_MODEL.md` describes end-to-end usage
- [ ] Intent vs execution separation is explicit
- [ ] Human-in-the-loop authority model documented
- [ ] Permissioned automation model described
- [ ] Session lifecycle documented

---

## 4. Prompt Integrity

For every prompt file:

- [ ] Clarifying questions required before generation
- [ ] Explicit prohibition on invention/hallucination
- [ ] Output format clearly defined
- [ ] No project- or tool-specific assumptions
- [ ] Prompt filenames use consistent naming

---

## 5. SDLC Coverage

Confirm AMP supports:

- [ ] Product Requirements Documents (PRDs)
- [ ] Architecture Decision Records (ADRs)
- [ ] Task generation
- [ ] Feature issue creation
- [ ] Bug issue creation
- [ ] Pull Request–based development
- [ ] CI / testing workflows
- [ ] Project tracking and hygiene

No missing phases.

---

## 6. Adoption & Onboarding

- [ ] `README.md` clearly explains what AMP is and is not
- [ ] Start-here documents exist and are referenced
- [ ] Failure modes are documented
- [ ] Intended audience is clearly defined
- [ ] Tool-agnostic stance is explicit

---

## 7. Lessons Learned & Guidance

- [ ] Oracle Review Pattern documented
- [ ] Human workflow setup documented
- [ ] Lessons learned are clearly labeled as optional
- [ ] No lessons presented as mandatory rules

---

## 8. Glossary & Shared Language

- [ ] Glossary exists and is comprehensive
- [ ] Key terms used consistently across documents
- [ ] Ambiguous terminology resolved

---

## 9. Licensing & Legal

- [ ] `LICENSE` file present (MIT)
- [ ] License referenced in README
- [ ] No conflicting license text elsewhere
- [ ] Attribution language aligned with license intent

---

## 10. Contribution Readiness

- [ ] `CONTRIBUTING.md` exists
- [ ] Contribution philosophy documented
- [ ] Licensing terms for contributions stated
- [ ] No implied ownership ambiguity

---

## 11. Versioning & Metadata

- [ ] `VERSION` file set to `1.0.0`
- [ ] `CHANGELOG.md` includes v1.0.0 entry
- [ ] Repo description updated
- [ ] Tags follow semantic versioning

---

## 12. Final Sanity Check

- [ ] Repository reviewed from a first-time user perspective
- [ ] No internal-only language remains
- [ ] No placeholders or empty documents
- [ ] All links resolve correctly
- [ ] Everything in v1.0 is intentional

---

## Release

- [ ] Tag `v1.0.0`
- [ ] Push tag to origin
- [ ] Publish GitHub release notes

---

## Final Note

v1.0 establishes the **stable core** of AMP Operating Protocol.
Future versions may extend functionality, but core invariants
should change rarely and deliberately.
