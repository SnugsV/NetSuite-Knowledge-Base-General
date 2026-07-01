# Documentation Standards

## Purpose

Define the structure, metadata, and formatting rules for every article in this repository. Consistency across articles improves readability for humans and retrievability for AI systems.

## Article Structure

Every article should follow this standard structure. Sections marked with * are required; others are recommended when relevant.

```markdown
---
title: Article Title
module: Module Name
difficulty: Beginner | Intermediate | Advanced
estimated_time: X minutes
status: Draft | Review | Approved
last_reviewed: YYYY-MM-DD
---

# Article Title *

## Quick Summary *       (1-3 sentences explaining the article)
## Difficulty *          (Beginner, Intermediate, or Advanced)
## Estimated Time *      (Expected reading/completion time)
## Prerequisites         (Required knowledge, permissions, setup)
## Overview *            (What this topic is about)
## Why It Matters        (Business problem it solves)
## Core Concepts         (Key ideas explained)
## Step-by-Step          (Procedural instructions, if applicable)
## Best Practices        (Recommended approaches)
## Common Mistakes *     (What people get wrong)
## FAQ                   (Frequently asked questions)
## Related Articles *    (Cross-links to related content)
## Oracle References *   (Links to authoritative Oracle docs)
```

## Heading Hierarchy

- Use one H1 (`#`) per article — the article title
- Use H2 (`##`) for major sections
- Use H3 (`###`) for subsections
- Use H4 (`####`) sparingly, only for deep nesting
- Every H2 should contain at least one sentence of content

## Cross-Linking

Every article must link to related content. Cross-linking turns individual articles into a connected knowledge network.

### Rules

- Add a "Related Articles" section at the bottom of every article
- Use relative paths: `[Navigation](../navigation.md)` or `[Inventory Overview](../docs/inventory/overview.md)`
- Each article should link to at least 3-5 related articles
- Link to articles in other modules where relevant (e.g., a SuiteScript article linking to Saved Searches)
- Avoid duplicate links within the same article
- Verify all links point to existing files before committing

### Cross-Link Target Types

- **Within module**: `[Navigation](../navigation.md)` — same directory
- **Between modules**: `[Saved Searches](../docs/saved-searches/overview.md)` — parent directory
- **To root docs**: `[License](../../LICENSE.md)` — two levels up
- **To framework**: `[Standards](MASTER_PROJECT_PROMPT.md)` — framework references

## Oracle References

Every article that describes NetSuite functionality must include an Oracle references section.

- Provide direct links to the relevant Oracle NetSuite Help Center pages
- Also reference SuiteAnswers where applicable
- The link text should describe the resource, not just say "Oracle docs"
- Keep links at the end of the article, not inline

## Examples

Include practical, real-world examples where possible.

- Use business scenarios that illustrate the concept
- Show both basic and advanced usage
- Label examples clearly
- Use code blocks for UI paths, formulas, or scripts

## FAQ

Include FAQ sections when there are common questions the article answers. This improves AI retrievability because FAQ entries are often the most searched-for content.

## Business Use Cases

Explain when and why a user would use this feature. Business context helps readers understand applicability.

## Best Practices

List recommended approaches and configurations. Best practices should be actionable, not abstract.

## Terminology

- Define acronyms on first use in each article
- Use the [Glossary](../docs/getting-started/glossary.md) for term definitions
- Be consistent with terminology across the project

## Naming Conventions

| Element | Convention | Example |
|---|---|---|
| File names | Lowercase hyphen-separated | `inventory-transfers.md` |
| Directory names | Lowercase hyphen-separated | `getting-started/` |
| Article titles | Sentence case | `What Is NetSuite?` |
| Headings | Sentence case | `Why It Matters` |
| Front matter keys | Lowercase with underscores | `estimated_time`, `last_reviewed` |

## Metadata (Front Matter)

Every stable article includes YAML front matter:

```yaml
---
title: Inventory Transfers
module: Inventory
difficulty: Beginner
estimated_time: 5 minutes
status: Draft
last_reviewed: 2026-07-01
---
```

Required fields: `title`, `module`, `difficulty`, `estimated_time`, `status`
Recommended fields: `last_reviewed`, `tags`

## Related Documents

- [WRITING_STANDARDS.md](WRITING_STANDARDS.md) — Tone, voice, teaching
- [AI_STANDARDS.md](AI_STANDARDS.md) — AI/LLM/RAG optimization
- [REVIEW_CHECKLIST.md](REVIEW_CHECKLIST.md) — Validation checklist
- [QUALITY_STANDARDS.md](QUALITY_STANDARDS.md) — Quality scoring