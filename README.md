# NetSuite Knowledge Base General

> Community-driven, AI-friendly documentation for NetSuite administrators, developers, consultants, business users, and students.

## Mission

The NetSuite Knowledge Base General project exists to make NetSuite easier to learn, implement, administer, and automate.

This repository complements Oracle's official documentation by providing original explanations, implementation guidance, best practices, troubleshooting notes, and AI-friendly Markdown. It does not replace Oracle's official documentation.

## Who This Is For

- NetSuite administrators
- Developers and SuiteScript users
- Consultants and implementation teams
- Finance and accounting teams
- Sales, purchasing, inventory, and manufacturing users
- Business owners evaluating or operating NetSuite
- AI assistants and knowledge-base systems

## Project Goals

- Beginner-friendly learning paths
- Practical implementation guidance
- AI-optimized Markdown structure
- Cross-linked articles
- Best practices and common mistakes
- Clear references to official Oracle documentation
- Version-controlled community knowledge

## Repository Structure

```text
/                         Root project tracking and governance files
knowledge-engine/         AI Knowledge Engineering Framework (permanent operating system)
docs/                     Main knowledge base articles by module
templates/                Reusable article and guide templates
governance/               Writing, review, and AI documentation standards
sources/                  Official Oracle documentation reference index
assets/                   Diagrams, images, icons, and supporting files
```

## Knowledge Engineering Framework

The [knowledge-engine/](knowledge-engine/README.md) directory contains the complete AI Knowledge Engineering Framework — the permanent operating system for all work on this repository. It eliminates the need for long prompts by moving all project knowledge into version-controlled documentation.

**Key documents:**

- [MASTER_PROJECT_PROMPT.md](knowledge-engine/MASTER_PROJECT_PROMPT.md) — Single reference for all future prompts
- [OPERATING_PROCEDURE.md](knowledge-engine/OPERATING_PROCEDURE.md) — Hermes startup sequence
- [DOCUMENTATION_STANDARDS.md](knowledge-engine/DOCUMENTATION_STANDARDS.md) — Article and metadata standards
- [REVIEW_CHECKLIST.md](knowledge-engine/REVIEW_CHECKLIST.md) — PR review checklist
- [PROMPT_LIBRARY.md](knowledge-engine/PROMPT_LIBRARY.md) — Example prompts for common tasks

Future prompts should be as simple as: "Read the Knowledge Engineering Framework and build Release X."

## Learning Paths

### Beginner

Start with NetSuite concepts, navigation, roles, dashboards, records, and global search.

### Intermediate

Move into inventory, purchasing, sales, reporting, saved searches, CSV imports, and workflows.

### Advanced

Explore SuiteScript, SuiteTalk, integrations, SuiteAnalytics, automation, and advanced administration.

## AI-Friendly Documentation

Every article should be structured so both humans and AI assistants can retrieve useful information quickly.

A strong article includes:

- Quick summary
- Difficulty level
- Estimated time
- Prerequisites
- Step-by-step guidance
- Best practices
- Common mistakes
- FAQs
- Related articles
- Oracle references

## Company-Specific Overlays

This general repository can later be paired with private company-specific repositories. For example:

```text
NetSuite-Knowledge-Base-General
NetSuite-Knowledge-Base-HBS-Private
```

The general repository explains how NetSuite works. The private repository explains how a specific company uses NetSuite — including internal SOPs, custom fields, saved searches, and screenshots. This keeps general knowledge shareable while protecting proprietary information.

## Disclaimer

Oracle, NetSuite, SuiteScript, SuiteTalk, and related trademarks belong to Oracle Corporation. This repository is community-maintained and is not affiliated with or endorsed by Oracle. Official Oracle documentation should always be treated as the authoritative source.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) and the governance documents before submitting new content.

## Roadmap

See [ROADMAP.md](ROADMAP.md).
