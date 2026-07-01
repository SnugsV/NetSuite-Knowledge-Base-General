# Master Project Prompt

## Purpose

This document is the permanent operating instructions for any AI agent working on this project. It consolidates all project knowledge into a single reference. Future prompts should reference this document rather than reproduce instructions.

## Project Vision

A community-driven, AI-friendly, version-controlled knowledge base for NetSuite administrators, developers, consultants, and business users. This project makes NetSuite easier to learn, implement, administer, and automate by providing original explanations, implementation guidance, and cross-linked content optimized for both human readers and AI assistants.

## Philosophy

1. **Teach before instructing** — Explain *why* something exists before *how* to use it
2. **Original content** — All content must be original. Reference Oracle documentation, do not copy it
3. **Source-linked accuracy** — Every claim about NetSuite behavior should link to authoritative Oracle documentation
4. **Beginner-friendly depth** — Accessible to new users while valuable for experienced consultants
5. **Progressive enhancement** — Build learning paths from foundational to specialized knowledge
6. **Cross-link everything** — Every article connects to related topics

## Repository Standards

### Repository Architecture

```
/                             Root project tracking and governance files
docs/                         Main knowledge base articles by module
  getting-started/            Beginner learning path
  administration/             Users, roles, permissions, setup
  inventory/                  Items, locations, transfers
  saved-searches/             Search-driven reporting
  suitescript/                JavaScript customization
  suitetalk/                  REST and SOAP APIs
  (additional modules...)     
knowledge-engine/             AI Knowledge Engineering Framework
templates/                    Reusable article and guide templates
governance/                   Writing, review, and AI standards
sources/                      Official Oracle documentation reference index
```

### File Naming

- Lowercase words separated by hyphens
- Descriptive names that reflect content (not `overview.md` unless folder context is clear)
- Use `.md` extension for all documentation

### Front Matter

Every stable article includes YAML front matter:

```yaml
---
title: Article Title
module: Module Name
difficulty: Beginner | Intermediate | Advanced
estimated_time: X minutes
status: Draft | Review | Approved
last_reviewed: YYYY-MM-DD
---
```

## Documentation Philosophy

Every article should answer these questions:

- What is this?
- Why does it exist?
- When should I use it?
- How does it work?
- What mistakes do people make?
- Where can I learn more?

### Article Structure

```
# Title
## Quick Summary
## Difficulty
## Estimated Time
## Prerequisites (if needed)
## Overview
## Why It Matters
## Core Concepts
## Step-by-Step (if applicable)
## Best Practices
## Common Mistakes
## FAQ (if useful)
## Related Articles
## Oracle References
```

## Git Workflow

1. Branch from `main` using pattern `sprint/<name>` or `feature/<name>`
2. Perform work in logical commits
3. Push branch to origin
4. Open PR with `gh pr create`
5. After review, squash merge into `main`

## Release Process

Versions follow semantic versioning:

- **Major** — Significant scope expansion, restructuring
- **Minor** — New modules, new features, framework additions
- **Patch** — Bug fixes, link repairs, minor updates

## Review Expectations

Every PR must satisfy the [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md) before opening. Key checks:

- Content is original (not copied from Oracle)
- Oracle sources are linked where applicable
- Cross-links are present and valid
- Front matter is complete
- Spelling and grammar checked
- Project tracking files updated

## Quality Expectations

Repository health is measured on 7 criteria on a 1-10 scale:
- Structure, Governance, Templates, Content, Project Tracking, Automation, Readability

Target: **9/10** by Version 1.0.

## AI Collaboration

AI agents should:

- Read the Knowledge Engineering Framework before starting work
- Follow the OPERATING_PROCEDURE.md startup sequence
- Read PROJECT_MEMORY.md to understand context
- Use PROMPT_LIBRARY.md for prompt templates
- Verify all technical claims against official Oracle documentation
- Review AI-generated content against project standards
- Treat AI as a tool, not a replacement for human review of technical accuracy

## Project Memory

Before every task, read:

1. [PROJECT_STATUS.md](../PROJECT_STATUS.md) — Current state, health score, priorities
2. [SESSION_REPORT.md](../SESSION_REPORT.md) — What changed last session, lessons learned
3. [BACKLOG.md](../BACKLOG.md) — Planned sprints and pending work
4. [ROADMAP.md](../ROADMAP.md) — Long-term direction
5. [CHANGELOG.md](../CHANGELOG.md) — Version history
6. Recent pull requests on GitHub
7. Open issues on GitHub

## Continuous Improvement

- Update PROJECT_STATUS.md after every session
- Log lessons learned in SESSION_REPORT.md
- Add technical debt items as they are discovered
- Propose framework improvements via issues or PRs
- Update the PROMPT_LIBRARY.md as new task patterns emerge

## Stopping Conditions

Stop and request clarification when:

- The requested task conflicts with project standards
- The task involves high-risk architectural changes without approval
- The task requires proprietary or licensed information
- The task would require copying Oracle documentation verbatim
- Technical claims cannot be verified against authoritative sources

## Definition of Done

A task is complete when:

- All requested files exist and are properly formatted
- Cross-links to related content are present and valid
- Project tracking files (PROJECT_STATUS, SESSION_REPORT, BACKLOG, CHANGELOG) are updated
- Repository health score is recalculated
- All changes are committed to a branch
- A pull request is open for review
- The work does not violate any project standards

## Related Documents

- [OPERATING_PROCEDURE.md](OPERATING_PROCEDURE.md) — Detailed startup sequence
- [DOCUMENTATION_STANDARDS.md](DOCUMENTATION_STANDARDS.md) — Article and metadata standards
- [WRITING_STANDARDS.md](WRITING_STANDARDS.md) — Tone, voice, teaching philosophy
- [AI_STANDARDS.md](AI_STANDARDS.md) — AI optimization guidelines
- [DECISION_FRAMEWORK.md](DECISION_FRAMEWORK.md) — Decision-making rules
- [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md) — PR review requirements
- [QUALITY_STANDARDS.md](QUALITY_STANDARDS.md) — Quality metrics and scoring
- [PROMPT_LIBRARY.md](PROMPT_LIBRARY.md) — Example prompts