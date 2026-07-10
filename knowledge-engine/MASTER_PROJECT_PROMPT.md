# Master Project Prompt

## Purpose

This document is the permanent operating instructions for any AI agent working on this project. It consolidates project knowledge into a single reference for deeper framework work. For the shortest startup path, begin with the root [AGENTS.md](../AGENTS.md) guide.

## Project Vision

A community-driven, AI-friendly, version-controlled knowledge base for NetSuite administrators, developers, consultants, and business users. This project makes NetSuite easier to learn, implement, administer, and automate by providing original explanations, implementation guidance, and cross-linked content optimized for both human readers and AI assistants.

## Philosophy

1. **Teach before instructing** — Explain *why* something exists before *how* to use it
2. **Original content** — All content must be original. Reference Oracle documentation, do not copy it
3. **Source-linked accuracy** — Every claim about NetSuite behavior should link to authoritative Oracle documentation
4. **Beginner-friendly depth** — Accessible to new users while valuable for experienced consultants
5. **Progressive enhancement** — Build learning paths from foundational to specialized knowledge
6. **Cross-link everything** — Every article connects to related topics
7. **Public-safe by default** — Keep company-specific implementation details in private overlays or internal knowledge sources

## Public and Private Content Boundary

This public repository may explain general NetSuite concepts, broadly applicable implementation guidance, public-safe troubleshooting patterns, and AI reasoning structures.

Do not add private SOPs, customer examples, custom fields, saved searches, workflows, SuiteScripts, screenshots, pricing, credentials, proprietary processes, or details that reveal how a specific organization operates.

## Repository Standards

### Repository Architecture

```text
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

```text
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

- Content is original and not copied from Oracle
- Oracle sources are linked where applicable
- Cross-links are present and valid
- Front matter is complete where required
- Spelling and grammar are checked
- Public/private boundary rules are satisfied
- Project tracking files are updated when repository state changes

## Quality Expectations

Repository health is measured on 7 criteria on a 1-10 scale:

- Structure, Governance, Templates, Content, Project Tracking, Automation, Readability

Target: **9/10** by Version 1.0.

## AI Collaboration

AI agents should:

- Start with [AGENTS.md](../AGENTS.md)
- Read the Knowledge Engineering Framework before content or architecture work
- Follow [OPERATING_PROCEDURE.md](OPERATING_PROCEDURE.md) for repeatable maintenance workflow
- Read [PROJECT_MEMORY.md](PROJECT_MEMORY.md) when historical context is needed
- Use [PROMPT_LIBRARY.md](PROMPT_LIBRARY.md) for prompt templates
- Verify technical claims against official Oracle documentation
- Review AI-generated content against project standards
- Treat AI as a tool, not a replacement for human review of technical accuracy

## Project Memory

For broader planning or repository-state work, review:

1. [PROJECT_STATUS.md](../PROJECT_STATUS.md) — Current state, health score, priorities
2. [SESSION_REPORT.md](../SESSION_REPORT.md) — What changed last session, lessons learned
3. [BACKLOG.md](../BACKLOG.md) — Planned sprints and pending work
4. [ROADMAP.md](../ROADMAP.md) — Long-term direction
5. [CHANGELOG.md](../CHANGELOG.md) — Version history
6. Relevant GitHub issues and pull requests

## Continuous Improvement

- Update PROJECT_STATUS.md when repository state changes
- Log lessons learned in SESSION_REPORT.md when a session changes direction or creates technical debt
- Add technical debt items as they are discovered
- Propose framework improvements via issues or PRs
- Update PROMPT_LIBRARY.md as new task patterns emerge

## Stopping Conditions

Stop and request clarification when:

- The requested task conflicts with project standards
- The task involves high-risk architectural changes without approval
- The task requires proprietary or licensed information
- The task would require copying Oracle documentation verbatim
- Technical claims cannot be verified against authoritative sources

## Definition of Done

A task is complete when:

- Requested files exist and are properly formatted
- Cross-links touched by the work are valid
- Required project tracking updates are complete
- The work does not violate public/private boundary rules
- Changes are committed in a reviewable scope
- A pull request is open when the work uses a branch-based workflow

## Related Documents

- [AGENTS.md](../AGENTS.md) — AI-agent startup and public-safety guide
- [OPERATING_PROCEDURE.md](OPERATING_PROCEDURE.md) — Detailed startup sequence
- [DOCUMENTATION_STANDARDS.md](DOCUMENTATION_STANDARDS.md) — Article and metadata standards
- [WRITING_STANDARDS.md](WRITING_STANDARDS.md) — Tone, voice, teaching philosophy
- [AI_STANDARDS.md](AI_STANDARDS.md) — AI optimization guidelines
- [DECISION_FRAMEWORK.md](DECISION_FRAMEWORK.md) — Decision-making rules
- [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md) — PR review requirements
- [QUALITY_STANDARDS.md](QUALITY_STANDARDS.md) — Quality metrics and scoring
- [PROMPT_LIBRARY.md](PROMPT_LIBRARY.md) — Example prompts
