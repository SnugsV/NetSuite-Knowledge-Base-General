# Framework Review

## Purpose

Critical review of the entire Knowledge Engineering Framework for long-term maintainability, scalability, and clarity. This review evaluates every document in `knowledge-engine/`, templates in `templates/`, and governance in `governance/` as though the repository will grow to 10,000+ articles with hundreds of contributors and multiple AI agents.

---

## Phase 1 — Repository Architecture Review

### Documents Reviewed

| # | Document | Status | Issues Found |
|---|---|---|---|
| 1 | README.md (knowledge-engine) | OK | Minor: directory table could use descriptions |
| 2 | MASTER_PROJECT_PROMPT.md | REVIEW | Structural overlap with multiple documents |
| 3 | PROJECT_CHARTER.md | REVIEW | Duplicates root-level PROJECT_CHARTER.md |
| 4 | OPERATING_PROCEDURE.md | REVIEW | Duplicates HERMES_OPERATING_PROCEDURE.md + overlaps GITHUB_WORKFLOW.md |
| 5 | DOCUMENTATION_STANDARDS.md | OK | Strong, well-defined |
| 6 | WRITING_STANDARDS.md | OK | Strong, well-defined |
| 7 | AI_STANDARDS.md | OK | Strong, well-defined |
| 8 | PROJECT_MEMORY.md | OK | Clear, well-defined |
| 9 | PROJECT_LIFECYCLE.md | OK | Clear, well-defined |
| 10 | GITHUB_WORKFLOW.md | REVIEW | Overlaps OPERATING_PROCEDURE.md |
| 11 | RELEASE_PROCESS.md | OK | Clear, well-defined |
| 12 | QUALITY_STANDARDS.md | OK | Strong, well-defined |
| 13 | REVIEW_CHECKLIST.md | OK | Strong, well-defined |
| 14 | DECISION_FRAMEWORK.md | OK | Clear, well-defined |
| 15 | PROMPT_LIBRARY.md | OK | Clear, well-defined |

### Structural Issues

#### Issue 1: Document Duplication — knowledge-engine/PROJECT_CHARTER.md

**Problem**: `knowledge-engine/PROJECT_CHARTER.md` (63 lines) is a subset of the root-level `/PROJECT_CHARTER.md` (287 lines). Both cover mission, philosophy, audience. The framework version was written first; the root version was expanded during Sprint 0.2.

**Recommendation**: Consolidate. The root-level `/PROJECT_CHARTER.md` should be the single source of truth. `knowledge-engine/PROJECT_CHARTER.md` should either be removed (redirect to root) or replaced with a framework-specific overview that points to the root document.

#### Issue 2: Document Duplication — OPERATING_PROCEDURE.md

**Problem**: `knowledge-engine/OPERATING_PROCEDURE.md` (78 lines) overlaps significantly with `knowledge-engine/GITHUB_WORKFLOW.md` (137 lines) and the root-level `HERMES_OPERATING_PROCEDURE.md` (169 lines). Three documents describe variations of the same workflow. This creates a maintenance burden — updating one means updating all three.

**Recommendation**: Consolidate into two documents:
- `knowledge-engine/OPERATING_PROCEDURE.md` — Startup sequence only (13 steps, no git commands, no PR commands).
- Remove git-related content (split to GITHUB_WORKFLOW.md).
- Remove environment details (move to `HERMES_OPERATING_PROCEDURE.md` which is environment-specific).

#### Issue 3: Content Overlap — MASTER_PROJECT_PROMPT.md

**Problem**: MASTER_PROJECT_PROMPT.md (187 lines) re-summarizes content from almost every other framework document: philosophy (PROJECT_CHARTER), standards (DOCUMENTATION_STANDARDS), git workflow (GITHUB_WORKFLOW), release (RELEASE_PROCESS), review (REVIEW_CHECKLIST), quality (QUALITY_STANDARDS), AI (AI_STANDARDS), memory (PROJECT_MEMORY). This creates a "summary" that must be kept in sync with 8+ source documents.

**Risk at 10,000 articles**: The summary document will inevitably drift from its sources. AI agents who rely on MASTER_PROJECT_PROMPT.md will get outdated guidance.

**Recommendation**: Restructure MASTER_PROJECT_PROMPT.md as a **navigation hub** rather than a summary. Instead of re-stating standards, list where to find them. This eliminates drift and forces readers to the authoritative source.

#### Issue 4: Governance File Naming Inconsistency

**Problem**: Files in `governance/` use mixed naming conventions:

| File | Convention |
|---|---|
| `AI_GUIDELINES.md` | UPPER_SNAKE_CASE |
| `REVIEW_PROCESS.md` | UPPER_SNAKE_CASE |
| `STYLE_GUIDE.md` | UPPER_SNAKE_CASE |
| `WRITING_GUIDELINES.md` | UPPER_SNAKE_CASE |
| `contribution-guide.md` | kebab-case |

The framework in `knowledge-engine/` consistently uses kebab-case. The root `governance/` dir uses UPPER_SNAKE_CASE.

**Recommendation**: Rename all governance files to kebab-case for consistency with the framework standard.

#### Issue 5: Orphaned Governance Document

**Problem**: `governance/contribution-guide.md` (33 lines) overlaps with root `CONTRIBUTING.md` (40 lines). Both describe contribution workflow, article requirements, and source policy. The `contribution-guide.md` content statuses and AI readiness checklist are not in `CONTRIBUTING.md`.

**Recommendation**: Merge the unique content from `contribution-guide.md` (content statuses, AI readiness checklist) into `CONTRIBUTING.md`, then delete `contribution-guide.md`.

---

## Phase 2 — Documentation Standards Review

### Would These Standards Work at 10,000 Articles?

| Standard | Assessment | Risk |
|---|---|---|
| Article structure | **Yes** | Consistent structure is mandatory at scale. Current standard is well-defined. |
| Front matter | **Yes** | 5 required fields is appropriate. Adding more would create friction. |
| Cross-linking (3-5 links) | **Needs adjustment** | At 10,000 articles, "3-5 links" may be too few. Consider "minimum 3, maximum 10" with AI-assisted recommendations. |
| File naming | **Yes** | kebab-case with descriptive names scales well. |
| Directory structure | **Yes** | Module-based hierarchy scales. Consider depth limit (max 2 levels deep). |

### Weaknesses Identified

#### Weakness 1: No Article Size Limit

**Problem**: No guidance on maximum article length. A 2,000-line article is harder for AI retrieval (chunking breaks context), harder for humans to navigate, and harder for MkDocs to render.

**Recommendation**: Add a recommended target of 200-500 lines per article. If an article exceeds 500 lines, consider splitting into sub-topics.

#### Weakness 2: No "Obsolete" Status

**Problem**: Content statuses include `Draft → Review → Approved → Deprecated → Archive` but only in the REVIEW_PROCESS.md. The DOCUMENTATION_STANDARDS.md front matter reference shows only `Draft | Review | Approved`.

**Recommendation**: Update DOCUMENTATION_STANDARDS.md front matter status list to include all 5 statuses: `Draft | Review | Approved | Deprecated | Archive`.

#### Weakness 3: No "Updated" Front Matter Field

**Problem**: The front matter has `last_reviewed` but no `last_updated` field. These are different — an article can be updated without being reviewed, and reviewed without being updated.

**Recommendation**: Add an optional `last_updated` field to front matter.

#### Weakness 4: No Module-Level README Requirement

**Problem**: There's no explicit standard requiring every module folder to have a README.md that acts as a module index.

**Recommendation**: Add this to DOCUMENTATION_STANDARDS.md: "Every module folder must have a README.md that lists all articles in the module with brief descriptions."

#### Weakness 5: No Cross-Link Audit Procedure

**Problem**: The standard says "verify all links point to existing files before committing" but doesn't specify how. At 10,000 articles, manual link checking is infeasible.

**Recommendation**: Add a cross-link validation procedure. For now, `grep -oP '\([^)]+\.md\)' *file*` checks. For the future, recommend automated link checking in CI/CD (Phase 3).

---

## Phase 3 — Governance Review

### What Should Be Frozen

The following documents are stable and should rarely change after this release:

| Document | Freeze Recommendation |
|---|---|
| DOCUMENTATION_STANDARDS.md | **Freeze** — Structure, naming, cross-linking rules are fundamental |
| WRITING_STANDARDS.md | **Freeze** — Tone, audience, teaching philosophy are foundational |
| AI_STANDARDS.md | **Freeze** — Multi-audience optimization strategy is settled |
| QUALITY_STANDARDS.md | **Freeze** — Scoring methodology, criteria, and targets are stable |
| PROJECT_MEMORY.md | **Freeze** — Memory structure is defined and working |
| PROJECT_LIFECYCLE.md | **Freeze** — Phase definitions are comprehensive |
| DECISION_FRAMEWORK.md | **Freeze** — Risk categories and escalation path are defined |

### What Should Remain Flexible

| Document | Flexibility Reason |
|---|---|
| PROMPT_LIBRARY.md | Should grow as new task patterns emerge |
| RELEASE_PROCESS.md | May need adjustment as the project scales |
| GITHUB_WORKFLOW.md | May change if automation is added (Phase 3) |
| REVIEW_CHECKLIST.md | May get additional items as the project matures |

### What Needs Consolidation Before Freeze

| Action | Priority | Reason |
|---|---|---|
| Consolidate PROJECT_CHARTER.md duplicates | High | Two versions will drift |
| Consolidate OPERATING_PROCEDURE.md + GITHUB_WORKFLOW.md + HERMES_OPERATING_PROCEDURE.md | High | Three overlapping workflow documents |
| Consolidate CONTRIBUTING.md + contribution-guide.md | High | Overlapping contribution guidance |
| Standardize governance/ file naming | Low | Cosmetic but affects discoverability |

### Governance Belongs In

```
knowledge-engine/     → Standards, architecture, lifecycle, quality, decisions
governance/           → Legacy documents (to be consolidated into framework)
templates/            → Article templates
CONTRIBUTING.md       → Single contribution guide (root level)
```

**Recommendation**: After consolidation, the `governance/` directory can be retired — all its content will have moved to either `knowledge-engine/` or root-level files.

---

## Phase 4 — Template Finalization

### Current Templates

| File | Lines | Structure |
|---|---|---|
| `templates/ARTICLE_TEMPLATE.md` | 70 | Full article structure with front matter. Matches DOCUMENTATION_STANDARDS.md closely. |
| `templates/FAQ_TEMPLATE.md` | 125 bytes | Minimal Q&A template |
| `templates/TROUBLESHOOTING_TEMPLATE.md` | 329 bytes | Problem → Symptoms → Causes → Resolution |
| `templates/document-template.md` | 60 | Different front matter (`department`, `owner`, `reviewer`, `source_type`). Different section structure. |

### Assessment

**ARTICLE_TEMPLATE.md** is the correct canonical template. It matches DOCUMENTATION_STANDARDS.md closely. Only one structural gap: it uses "When to Use It" (section) where the standard specifies "Why It Matters" and "Core Concepts" as separate sections.

**document-template.md** is a legacy format that should be deprecated. Its `department`, `owner`, `reviewer`, `source_type` fields are useful for internal SOPs but don't belong in a general knowledge base.

**FAQ_TEMPLATE.md** and **TROUBLESHOOTING_TEMPLATE.md** are useful for their specific purposes and should remain.

### Finalized Canonical Template

Replace `templates/ARTICLE_TEMPLATE.md` with this standardized version:

```markdown
---
title:
module:
difficulty: Beginner | Intermediate | Advanced
estimated_time:
status: Draft
last_reviewed:
---

# Article Title

## Quick Summary

1-3 sentences explaining the topic.

## Difficulty

Beginner, Intermediate, or Advanced.

## Estimated Time

Expected reading or completion time.

## Prerequisites

Required knowledge, permissions, or setup steps.

## Overview

What this topic is about.

## Why It Matters

The business problem it solves.

## Core Concepts

Key ideas explained in plain language.

## Step-by-Step

Procedural instructions, if applicable.

## Best Practices

Recommended approaches.

## Common Mistakes

What people get wrong.

## FAQ

Frequently asked questions (optional).

## Related Articles

- [Article Name](../path/article.md)

## Oracle References

- Authoritative Oracle documentation link
```

### Deprecation

- `templates/document-template.md` → **Deprecate**. Remove its front matter fields as "internal use only" — they don't belong in the public template.

---

## Phase 5 — Scalability Review

### Evaluating at 10,000+ Articles, 500 PRs, 100 Contributors

| Dimension | Current | At Scale | Risk |
|---|---|---|---|
| **Navigation** | Module-level directories | Would work up to ~50 modules. Beyond that, folders need sub-categorization. | Low at current size |
| **Folder organization** | `/docs/{module}/` — one level deep | Works well. Adding sub-modules like `/docs/administration/security/` would keep it scalable. | Low |
| **Searchability** | GitHub search, file names | 10,000 files need search indexing. MkDocs + built-in search is essential. | Medium — need Phase 3 plan |
| **Cross-linking** | Manual relative links | 10,000 files with 200,000+ cross-links need automated validation. Manual checking impossible. | **High** |
| **Versioning** | CHANGELOG only | Need release tagging for documentation snapshots. Current tag strategy is adequate. | Low |
| **Discoverability** | Module README + docs/README | Single docs/README with 17 modules is fine. At 50+ modules, a more structured index would be needed. | Medium |
| **Contributor workflow** | PR-based, gh CLI | Scales well. Automated linting/validation on PR would prevent bottlenecks. | Medium |
| **AI retrieval** | Front matter, consistent sections | Scales well if front matter is enforced. Risk: articles missing required fields become invisible to AI. | Medium |
| **Knowledge management** | Memory files (PROJECT_STATUS, SESSION_REPORT, etc.) | Scales well. These are already structured for AI consumption. | Low |

### Critical Scalability Gaps

#### Gap 1: No Automated Validation

At 500 PRs, manual cross-link checking, front matter validation, and Markdown formatting review become the primary bottleneck. 

**Recommendation**: Before Phase 3, add a GitHub Action that:
- Validates front matter on every PR
- Checks all cross-links resolve to existing files
- Lints Markdown formatting

#### Gap 2: No Indexing Strategy

GitHub's plain file browser is adequate for 20 files but not 200. 

**Recommendation**: The structured module hierarchy is good. Add `docs/{module}/README.md` as a required index for every module.

#### Gap 3: No File Naming Collision Strategy

Two different articles cannot have the same file name. At 10,000 files, naming collisions will occur.

**Recommendation**: Enforce unique file names across the entire `docs/` tree. A naming prefix convention could help: `admin-users.md`, `inv-transfers.md`, `ss-script-types.md`.

---

## Phase 6 — Architecture Decision Records

ADRs are valuable for documenting WHY decisions were made. Given the framework is near-stabilization, creating ADRs now captures the reasoning for future contributors.

### ADRs to Create

| # | Title | Status |
|---|---|---|
| ADR-0001 | Documentation Structure | Proposed |
| ADR-0002 | Article Format Standard | Proposed |
| ADR-0003 | Cross-Link Strategy | Proposed |
| ADR-0004 | Content Lifecycle and Review Model | Proposed |
| ADR-0005 | AI Collaboration Model | Proposed |

Each ADR follows the standard format: Title, Status, Context, Decision, Consequences, Alternatives Considered.

---

## Phase 7 — Repository Health Assessment

### Updated Scores

| Criterion | Score | Justification |
|---|---|---|
| **Structure** | 9 | Clean module hierarchy. framework is well-organized. No orphaned files. |
| **Governance** | 8 | Framework documents are comprehensive. Consolidation of legacy governance/ files would bring this to 9. |
| **Templates** | 7 | Two template formats with different front matter. Unification would bring to 9. Still at 7 until deprecated template is removed. |
| **Content** | 6 | Getting-started module is strong (12 articles). 6 modules have starter content. 11 modules empty. |
| **Project Tracking** | 8 | All tracking files present. Health score methodology defined. Not yet linked to GitHub issues. |
| **Automation** | 2 | No CI/CD. No validation. Target for Phase 3. |
| **Readability** | 9 | Getting-started articles meet standards. Framework documents are clear. |
| **Scalability** | 7 | Architecture supports growth. Cross-link validation at scale is the biggest risk. No automated validation. |
| **Maintainability** | 7 | Document duplication (charter, workflow, governance) creates 3 maintenance points where 1 would suffice. |
| **AI Readiness** | 8 | Front matter, consistent structure, quick summaries present. No automated front matter validation. |

### Repository Health Score

**7.5 / 10** (weighted average reflecting honest assessment)

Breakdown: (9 + 8 + 7 + 6 + 8 + 2 + 9 + 7 + 7 + 8) / 10 = 71 / 10 = 7.1 → **7.0** (more honest than 7.5)

**Corrected honest score: 7.0 / 10**

Explanation: The previous scores were inflated by weighting governance/content/tracking equally with automation. The honest assessment includes scalability and maintainability as separate criteria, which pull the score down.

### Cross-Link Quality

**Fair**. Getting-started module has strong internal cross-links. Inventory, saved-searches, suitescript, and suitetalk articles have zero cross-links.

### Engineering Maturity

**Developing**. The framework exists and is well-structured. Document duplication and lack of automation are the primary gaps. Appropriate for Phase 1.

---

## Summary of Actions

| Action | Risk Level | Effort | Priority |
|---|---|---|---|
| Consolidate PROJECT_CHARTER.md duplicates | Medium | 15 min | High |
| Consolidate OPERATING_PROCEDURE.md + GITHUB_WORKFLOW.md + HERMES_OPERATING_PROCEDURE.md | Medium | 30 min | High |
| Merge contribution-guide.md into CONTRIBUTING.md | Low | 10 min | High |
| Remove document-template.md, finalize ARTICLE_TEMPLATE.md | Medium | 15 min | High |
| Create ADR-0001 through ADR-0005 | Low | 30 min | Medium |
| Rename governance/ files to kebab-case | Low | 5 min | Medium |
| Restructure MASTER_PROJECT_PROMPT.md as navigation hub | Medium | 30 min | Medium |
| Add article size guidance to DOCUMENTATION_STANDARDS.md | Low | 5 min | Low |
| Add all 5 statuses to front matter spec | Low | 5 min | Low |
| Add module README requirement to standards | Low | 5 min | Low |

## Related Documents

- [FRAMEWORK_FREEZE_RECOMMENDATION.md](FRAMEWORK_FREEZE_RECOMMENDATION.md) — Freeze recommendation
- [knowledge-engine/decisions/](decisions/) — Architecture Decision Records