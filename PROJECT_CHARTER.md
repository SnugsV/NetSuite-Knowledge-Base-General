# Project Charter

## Mission

The NetSuite Knowledge Base General project creates a community-driven, AI-friendly, and maintainable reference library for NetSuite administrators, developers, consultants, business users, and students.

This project complements Oracle's official documentation by providing original explanations, implementation guidance, best practices, troubleshooting notes, and cross-linked content optimized for both human readers and AI assistants. It does not replace Oracle's official documentation.

## Target Audience

- NetSuite administrators
- SuiteScript developers
- Consultants and implementation teams
- Finance, accounting, inventory, sales, and operations teams
- Business owners evaluating or operating NetSuite
- AI assistants and knowledge-base systems

---

## Repository Philosophy

### Documentation as Teaching

Every article should teach before instructing. A reader should understand *why* something exists before learning *how* to use it. Documentation that explains only the steps without the context leaves readers unable to adapt what they learn to their own situation.

### Original Content

All content in this repository must be original. Write summaries, explanations, and guides in your own words. Do not copy, mirror, or republish Oracle documentation. This project exists because official documentation is reference material; this project makes NetSuite *understandable*.

### Source-Linked Accuracy

Every article that references official Oracle material must include a link to the authoritative source. Prefer linking to the Help Center, SuiteAnswers, or the REST API Browser. A reader should be able to verify claims and dive deeper into official documentation.

### Beginner-Friendly Depth

Articles should be accessible to someone new to NetSuite while remaining valuable for experienced consultants. Use clear language, define acronyms, include practical examples, and mark advanced sections when needed.

### Progressive Enhancement

Start simple, then add complexity. A reader should not need to understand SuiteScript to understand inventory transfers. Build learning paths from foundational concepts toward specialized knowledge.

---

## Documentation Principles

1. **Teach before instructing** — Explain the concept, then show the steps.
2. **One topic per file** — Keep each file focused on one subject. Split long articles.
3. **Cross-link everything** — Every article should link to related topics.
4. **Front matter on stable content** — Use YAML front matter for metadata.
5. **Examples over abstractions** — Prefer real business scenarios.
6. **Common mistakes matter** — Include what people get wrong.
7. **Version awareness** — Note when content applies to specific NetSuite versions.

---

## Writing Standards

### Voice

Write like a knowledgeable NetSuite consultant teaching a new user. Be clear, practical, and direct. Use "you" when addressing the reader. Avoid promotional or marketing language.

### Article Structure

Every article should use consistent headings so readers and AI systems can find information quickly:

```markdown
# Article Title

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

### Metadata Format

Use YAML front matter for stable articles:

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

### Voice Rules

- One H1 per article
- Descriptive headings (not just "Overview" — use "What Is NetSuite?")
- Keep paragraphs short (3-5 sentences maximum)
- Define acronyms before using them
- Avoid copying vendor documentation
- Use lowercase-with-hyphens for file names
- Use relative links for cross-references

### Difficulty Levels

- **Beginner**: Basic concepts, navigation, everyday usage
- **Intermediate**: Configuration, reporting, operational workflows
- **Advanced**: Scripting, integrations, architecture, complex administration

---

## AI Documentation Standards

AI assistants may be used to research, write, edit, and review documentation. When working with AI:

1. Provide clear context about the project, target audience, and module
2. Verify all technical claims against official Oracle documentation
3. Ensure all Oracle references are accurate links
4. Review AI-generated content for consistency with the project style guide
5. Treat AI as a tool, not a replacement for human review of technical accuracy

An AI-friendly article answers these questions clearly:

- What is this?
- Why does it exist?
- When should I use it?
- How does it work?
- What mistakes do people make?
- Where can I learn more?

Good AI retrieval requires consistent structure, unique file names, clear headings, and complete front matter.

---

## Review Standards

### Content Statuses

| Status | Meaning |
|---|---|
| **Draft** | Work in progress; not ready for AI or end-user use |
| **Review** | Ready for a human reviewer to validate |
| **Approved** | Reviewed and ready for AI/search/end-user use |
| **Deprecated** | Replaced by newer content |
| **Archive** | Historical content kept for reference |

### Review Checklist

Before a document moves to **Approved**, confirm:

1. Uses the standard template structure
2. Content is original, not copied from Oracle docs
3. Oracle sources are linked where applicable
4. Filed in the correct docs/ subfolder
5. Front matter metadata is complete
6. Clear separation between general NetSuite behavior and company-specific practices
7. Cross-links to related articles are present
8. Common mistakes section is present (even if brief)
9. Spelling and grammar checked

---

## Git Standards

### Branch Naming

- `main` — protected, production-ready content
- `sprint/<name>` — planned sprint branches
- `feature/<name>` — focused additions or fixes

### Workflow

1. Create a branch from `main`
2. Do all work on the branch
3. Open a pull request
4. Request review
5. Squash merge into `main`

### Commit Messages

Describe what changed and why. Preferred format:

```
Short summary (50 chars max)

Optional longer description explaining motivation.
```

### What Not to Do

- No direct commits to `main`
- No force pushes to shared branches
- No large binary files in the repository
- No vendor documentation copying

---

## Decision Making

### Low-Risk Changes

Implement without approval:

- Typo fixes, formatting corrections, broken link repairs
- Adding cross-links between existing articles
- Minor wording improvements that don't change meaning
- Removing placeholder content from empty folders

### Medium-Risk Changes

Document as a recommendation; do not implement without review:

- Renaming folders or restructuring docs/ hierarchy
- Adding new module categories
- Changing the template or metadata format
- Consolidating governance documents

### High-Risk Changes (Require Approval)

- Adding CI/CD, GitHub Actions, or automation
- Adding MkDocs, GitHub Pages, or any publishing pipeline
- Changing the repository license
- Adding company-specific or proprietary content to the general repo
- Large-scale content migration or deletion

---

## Repository Architecture

```
/                             Root project tracking and governance files
docs/                         Main knowledge base articles by module
  getting-started/            Beginner learning path
  administration/             Users, roles, permissions, setup
  accounting/                 Financial modules
  crm/                        Customer management
  inventory/                  Items, locations, transfers
  manufacturing/              Production and assembly
  purchasing/                 Vendor and procurement
  sales/                      Orders and revenue
  reporting/                  Financial and operational reports
  saved-searches/             Search-driven reporting
  suiteanalytics/             Analytics workbench
  suitescript/                JavaScript customization
  suitetalk/                  REST and SOAP APIs
  workflows/                  Approvals and automation
  integrations/               External system connections
  release-notes/              Version tracking
  troubleshooting/            Common issues and resolutions
templates/                    Reusable article and guide templates
governance/                   Writing, review, and AI documentation standards
sources/                      Official Oracle documentation reference index
assets/                       Diagrams, images, icons, and supporting files
```

---

## Oracle Documentation Policy

Oracle NetSuite's official documentation is the authoritative source for technical accuracy. This project:

- **References** Oracle documentation but does not reproduce it
- **Links** to official sources for deeper reading
- **Summarizes** concepts in original language for learning and quick reference
- **Does not** scrape, republish, or mirror Oracle documentation

---

## Licensing

Content in this repository is available for community use. See [LICENSE.md](LICENSE.md) for details.