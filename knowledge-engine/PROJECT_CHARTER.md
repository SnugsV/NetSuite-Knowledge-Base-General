# Project Charter

## Mission

The NetSuite Knowledge Base General project creates a community-driven, AI-friendly, and maintainable reference library for NetSuite administrators, developers, consultants, business users, and students.

This project complements Oracle's official documentation by providing original explanations, implementation guidance, best practices, troubleshooting notes, and cross-linked content optimized for both human readers and AI assistants. It does not replace Oracle's official documentation.

## Engineering Mindset

We build documentation with the same rigor as software:

- **Version-controlled** — All content tracked through Git
- **Reviewable** — Every change goes through a PR review
- **Testable** — Cross-links and front matter are validated
- **Maintainable** — Consistent structure enables automated processing
- **Scalable** — The framework supports growth from 10 to 10,000 articles

## Target Audience

- NetSuite administrators
- SuiteScript developers
- Consultants and implementation teams
- Finance, accounting, inventory, sales, and operations teams
- Business owners evaluating or operating NetSuite
- AI assistants and knowledge-base systems

## Repository Philosophy

### Documentation as Teaching

Every article should teach before instructing. A reader should understand *why* something exists before learning *how* to use it.

### Original Content

All content must be original. Summarize, explain, and teach — never copy, mirror, or republish Oracle documentation.

### Source-Linked Accuracy

Every article that references official Oracle material must include a link to the authoritative source. Verify all technical claims.

### Beginner-Friendly Depth

Accessible to new users while valuable for experienced consultants. Define acronyms, include examples, mark advanced sections.

### Progressive Enhancement

Start simple, then add complexity. Build learning paths from foundational concepts toward specialized knowledge.

## Core Principles

1. **Teach before instructing** — Explain the concept, then show the steps
2. **One topic per file** — Split long articles
3. **Cross-link everything** — Every article connects to related topics
4. **Front matter on stable content** — YAML metadata for AI retrievability
5. **Examples over abstractions** — Prefer real business scenarios
6. **Common mistakes matter** — Include what people get wrong
7. **Version awareness** — Note when content applies to specific NetSuite versions
8. **AI-friendly structure** — Consistent headings and metadata for LLM/RAG systems

## Related Documents

- [MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md) — Full project operating instructions
- [OPERATING_PROCEDURE.md](OPERATING_PROCEDURE.md) — Hermes startup sequence