# AI Documentation Guidelines

This repository is designed to be useful for human readers and AI assistants.

## Why AI-Friendly Formatting Matters

AI systems retrieve information more accurately when documents are structured consistently, use clear headings, and avoid mixing unrelated topics in one file.

## Guidelines

- Keep one primary topic per article.
- Use consistent section names across articles.
- Include a quick summary near the top.
- Add metadata where appropriate.
- Use descriptive file names.
- Link related articles.
- Avoid vague titles like `overview.md` unless the folder context is clear.
- Include common mistakes and FAQs because these answer real user questions.
- Separate official references from original explanation.

## Good AI Retrieval Pattern

An article should make it easy to answer:

- What is this?
- Why does it matter?
- When should it be used?
- What are the prerequisites?
- What are the steps?
- What mistakes should be avoided?
- What related topics should be reviewed?

## Metadata Recommendation

Use front matter when the document is stable enough:

```yaml
---
title: Inventory Transfers
module: Inventory
difficulty: Beginner
estimated_time: 5 minutes
status: Draft
last_reviewed: YYYY-MM-DD
---
```
