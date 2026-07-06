# Maintainer Guide

This guide explains how to maintain the NetSuite Knowledge Base General repository as a long-term public knowledge platform.

It is not a contributor guide. Contributor instructions belong in `CONTRIBUTING.md`. This document is for maintainers, reviewers, and AI agents responsible for keeping the repository accurate, organized, and useful.

## Repository Purpose

This repository provides original, AI-friendly NetSuite educational documentation. It teaches general NetSuite concepts, workflows, implementation patterns, troubleshooting approaches, and AI reasoning structures.

It should remain general and public-safe. Company-specific processes, proprietary screenshots, customer/vendor details, pricing logic, custom fields, saved searches, SuiteScripts, and internal SOPs belong in private overlay repositories.

## Public vs. Private Content Rule

Use this rule when deciding whether content belongs here:

> If publishing the content would help competitors understand how a specific company operates, keep it private. If it explains general NetSuite concepts or broadly applicable implementation guidance, it may belong in this public repository.

### Public Content Examples

- General NetSuite concepts
- Generic implementation guidance
- General saved search education
- General SuiteScript and SuiteTalk explanations
- Public-safe troubleshooting patterns
- AI reasoning frameworks that do not reveal proprietary business logic

### Private Content Examples

- Company-specific saved searches
- Custom fields and custom records unique to a business
- Internal workflows and SOPs
- Customer, vendor, pricing, or manufacturing details
- Screenshots from private NetSuite accounts
- Internal AI prompts or automation logic tuned to a private business
- Proprietary integration configurations

## Maintainer Responsibilities

Maintainers are responsible for:

1. Keeping project tracking files aligned.
2. Reviewing new content for accuracy, originality, and public safety.
3. Ensuring articles follow the canonical template and metadata standards.
4. Checking links, cross-references, and module indexes.
5. Keeping roadmap, backlog, status, changelog, and session reports separated by purpose.
6. Reviewing whether new content belongs in the public repository or a private overlay.
7. Maintaining repository health and AI-readiness.

## Tracking File Responsibilities

Each tracking file has a specific purpose:

| File | Purpose |
|---|---|
| `PROJECT_STATUS.md` | Current snapshot of repository state, risks, health, and active priorities. |
| `ROADMAP.md` | Future direction and phased plans only. |
| `BACKLOG.md` | Actionable work queue and planned tasks. |
| `CHANGELOG.md` | Release history only. |
| `SESSION_REPORT.md` | Current or most recent maintenance session log. |
| `KNOWN_GAPS.md` | Missing content, weak areas, and unresolved documentation gaps. |
| `REPOSITORY_HEALTH.md` | Health scoring model and latest repository health assessment. |

Avoid duplicating the same information across multiple tracking files unless the file has a clear reason to reference it.

## Maintenance Cadence

### Every Maintenance Session

1. Pull or review the latest state of `main`.
2. Read `PROJECT_STATUS.md`.
3. Read `SESSION_REPORT.md`.
4. Review the current branch and recent PR history.
5. Identify whether the task is content, governance, navigation, automation, or architecture work.
6. Make focused changes in a branch.
7. Update affected tracking files.
8. Review the diff before merging.

### Monthly

1. Review repository health score.
2. Check broken links.
3. Review stale tracking files.
4. Review missing license, governance, or automation tasks.
5. Audit recently added articles for metadata and cross-links.
6. Review whether any content should be moved to a private overlay.

### Quarterly

1. Review major NetSuite release changes.
2. Reassess roadmap priorities.
3. Review architecture and AI framework assumptions.
4. Evaluate automation improvements.
5. Review public/private boundary rules.

## Branch Strategy

Use focused branches with clear names:

| Work Type | Branch Pattern |
|---|---|
| Maintenance | `maintenance/<topic>` |
| Documentation | `docs/<module-or-topic>` |
| Feature or framework work | `feature/<topic>` |
| Release preparation | `release/<version-or-topic>` |
| Fixes | `fix/<issue-or-topic>` |

Keep branches focused. Avoid mixing content creation, governance cleanup, and automation changes in the same branch unless they are part of a planned release.

## Commit Guidelines

Use clear commit messages that describe the outcome, not just the action.

Good examples:

- `Update project status for Phase 1 cleanup`
- `Repair documentation index navigation`
- `Add CC BY 4.0 license`
- `Create repository health scoring model`

Avoid vague messages such as:

- `updates`
- `fix stuff`
- `changes`

## Definition of Done for Articles

An article is not complete until it has:

- One clear H1 title
- YAML front matter
- Quick summary
- Difficulty level
- Estimated time
- Prerequisites, if applicable
- Plain-language explanation
- Business context
- Core concepts
- Practical steps or examples where useful
- Best practices
- Common mistakes
- FAQ, if useful
- Related articles
- Oracle references where applicable
- Public-safe content review

## Definition of Done for Maintenance Work

Maintenance work is complete when:

- The intended files are updated.
- Tracking documents remain consistent.
- Links changed by the work are reviewed.
- No obvious public/private boundary issue was introduced.
- The changelog or session report is updated if appropriate.
- The branch diff is coherent and reviewable.

## AI Agent Maintenance Procedure

When an AI agent works on this repository, it should:

1. Read `README.md`.
2. Read `PROJECT_STATUS.md`.
3. Read `SESSION_REPORT.md`.
4. Read `ROADMAP.md` and `BACKLOG.md` if planning work.
5. Read `knowledge-engine/README.md` and `knowledge-engine/MASTER_PROJECT_PROMPT.md` if doing content or architecture work.
6. Make small, reviewable changes.
7. Avoid inventing NetSuite facts without source review.
8. Avoid adding company-specific or proprietary information to the public repository.
9. Update tracking files only when the change affects repository state.
10. Clearly report any tool limitation or uncertainty.

## Public Safety Review

Before merging content, ask:

1. Does this reveal how a specific company operates?
2. Does this include screenshots, IDs, names, saved search formulas, workflows, or scripts from a private account?
3. Does this expose pricing, customers, vendors, manufacturing logic, or operational strategy?
4. Would a competitor gain specific operational insight from this content?
5. Should this instead live in a private overlay repository?

If the answer to any of these is yes, do not publish the content here.

## License Guidance

This repository uses CC BY 4.0 for public documentation unless otherwise noted.

Code examples or future utility scripts may require separate license treatment. If the repository later includes substantial reusable code, consider clarifying that code examples are available under MIT while documentation remains CC BY 4.0.

## Long-Term Direction

This repository should evolve from a static documentation library into a NetSuite Intelligence Platform:

- ERP curriculum
- Support intelligence
- Customer context methodology
- AI skills
- Solution architecture reasoning
- Customer metadata requirements
- Integration intelligence
- Validation and benchmark frameworks

The goal is not only to explain NetSuite, but to help humans and AI systems reason through NetSuite problems in a structured, accurate, and public-safe way.
