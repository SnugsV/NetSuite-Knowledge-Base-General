# Article Classification

This document defines the standard article types for the NetSuite Knowledge Base General repository.

Article classification describes the purpose of a document. It complements:

- [KNOWLEDGE_DOMAINS.md](KNOWLEDGE_DOMAINS.md) - what the article is about
- [KNOWLEDGE_LEVELS.md](KNOWLEDGE_LEVELS.md) - how deep the article goes
- [PUBLIC_SAFETY_RULES.md](PUBLIC_SAFETY_RULES.md) - what must remain out of the public repository

Together, these create a simple taxonomy:

- Domain = subject area
- Level = depth and audience
- Article type = purpose and format

## Purpose

Article classification helps maintainers, contributors, and AI assistants decide:

1. What the reader should get from the article.
2. How the article should be structured.
3. Whether the article should explain, teach, guide, troubleshoot, compare, or document a pattern.
4. Which template or review checklist should apply.
5. How the article should be retrieved by AI systems later.

## Core Principle

Each article should have one primary article type.

An article may contain small elements from other types, but its main purpose should be clear. A troubleshooting article may include a short concept explanation, but it should still be classified as troubleshooting if its primary goal is diagnosis and resolution.

## Article Type Summary

| Article Type | Purpose | Typical Use |
|---|---|---|
| Concept | Explain what something is and why it matters. | Definitions, foundations, terminology, module overviews |
| Tutorial | Teach through a guided learning sequence. | Beginner walkthroughs, learning path lessons |
| How-To Guide | Show how to complete a specific task. | Administrative tasks, user procedures, configuration steps |
| Reference | Provide structured facts for lookup. | Field explanations, record summaries, API concept lists |
| Troubleshooting | Diagnose and resolve problems. | Errors, failed transactions, missing data, integration issues |
| Best Practice | Recommend a preferred approach. | Governance, security, reporting, implementation standards |
| FAQ | Answer common questions directly. | Repeated beginner or support questions |
| Decision Framework | Help choose between options. | Workflow vs script, report vs saved search, configure vs customize |
| Architecture Pattern | Describe reusable solution structure. | Cross-system design, knowledge architecture, integration patterns |
| Implementation Guide | Plan or execute a larger solution. | Module rollout, process design, phased implementation |

## Article Types

### Concept

Use a Concept article to explain what something is, where it fits, and why it matters.

Good uses:

- What is a saved search?
- What is a sales order?
- What is a role?
- What is SuiteScript?

Avoid turning concept articles into long task procedures. Link to how-to guides when execution details are needed.

### Tutorial

Use a Tutorial article to teach a reader through a guided sequence.

Good uses:

- A beginner learning path lesson
- A step-by-step introduction to a module
- A guided walkthrough that builds understanding over time

Tutorials should be educational and progressive, not just a checklist.

### How-To Guide

Use a How-To Guide when the main goal is helping a reader complete a specific task.

Good uses:

- How to create a saved search
- How to review user permissions
- How to use release preview
- How to update a dashboard portlet

How-to guides should be task-focused, practical, and scoped tightly.

### Reference

Use a Reference article when the reader needs structured information for lookup.

Good uses:

- Record type summaries
- Common transaction statuses
- Saved search formula concepts
- SuiteScript script type overview
- Glossary entries

Reference articles should be accurate, organized, and easy to scan.

### Troubleshooting

Use a Troubleshooting article when the reader needs to diagnose and resolve a problem.

Good uses:

- Why a transaction is not appearing in a saved search
- Why an integration failed
- Why inventory quantity looks incorrect
- Why a user cannot access a record

Troubleshooting articles should include symptoms, likely causes, evidence to gather, and safe resolution paths.

### Best Practice

Use a Best Practice article when the repository recommends a preferred approach.

Good uses:

- Saved search naming guidance
- Permission review practices
- Public-safe documentation standards
- Release preview review practices
- Integration error handling practices

Best practices should explain the reasoning behind the recommendation.

### FAQ

Use an FAQ article when the goal is to answer repeated questions quickly.

Good uses:

- Common beginner questions
- Common saved search questions
- Common administration questions
- Common integration concept questions

FAQ answers should be direct and link to deeper articles when needed.

### Decision Framework

Use a Decision Framework article when the reader must choose between options.

Good uses:

- Workflow vs SuiteScript
- Saved search vs report vs workbook
- Configuration vs customization
- Manual process vs automation
- Native feature vs integration

Decision frameworks should define criteria, tradeoffs, risks, and recommended next steps.

### Architecture Pattern

Use an Architecture Pattern article to describe a reusable solution structure.

Good uses:

- Integration architecture patterns
- Public/private repository overlay pattern
- AI retrieval architecture
- Knowledge graph relationship pattern
- Cross-module solution pattern

Architecture patterns should be reusable across organizations and must not expose private implementation details.

### Implementation Guide

Use an Implementation Guide when the article supports a larger rollout or project.

Good uses:

- Implementing a new module
- Planning an integration
- Rolling out a reporting strategy
- Preparing a phased automation project
- Designing a cross-functional business process

Implementation guides should include scope, prerequisites, phases, risks, validation, and handoff considerations.

## Assignment Rules

1. Choose one primary article type.
2. Choose the type based on the article's main job, not every section it contains.
3. Use Concept when the article explains what something is.
4. Use How-To Guide when the article helps the reader complete a specific task.
5. Use Troubleshooting when the article starts from a problem or symptom.
6. Use Decision Framework when the article helps choose between options.
7. Use Architecture Pattern when the article describes reusable structure.
8. Use Implementation Guide when the article supports a larger project or rollout.
9. Keep FAQs short and link to deeper articles instead of duplicating full guidance.
10. Do not include private company-specific details in any article type.

## Metadata Recommendation

Future articles should include article type metadata when structured front matter is adopted.

Example:

```yaml
primary_domain: Reporting & Analytics
related_domains:
  - Financial Management
knowledge_level: 300
article_type: how-to-guide
public_safety_review: required
```

Until formal metadata is adopted, reviewers should still classify each article by domain, knowledge level, and article type during review.

## Public-Safe Reminder

Article type does not change public-safety requirements.

Troubleshooting articles, implementation guides, architecture patterns, and decision frameworks can accidentally expose private operating logic if they use real examples. Keep all examples generic.

Do not include private screenshots, customer names, vendor names, saved search IDs, custom field IDs, workflow IDs, script IDs, account URLs, credentials, pricing logic, manufacturing logic, proprietary mappings, or internal procedures.

When in doubt, apply [PUBLIC_SAFETY_RULES.md](PUBLIC_SAFETY_RULES.md).
