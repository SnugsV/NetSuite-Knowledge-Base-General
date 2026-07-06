# Knowledge Relationships

This document defines the standard relationship types used to connect articles in the NetSuite Knowledge Base General repository.

Knowledge relationships describe how documents connect to each other. They complement:

- [KNOWLEDGE_DOMAINS.md](KNOWLEDGE_DOMAINS.md) - what the article is about
- [KNOWLEDGE_LEVELS.md](KNOWLEDGE_LEVELS.md) - how deep the article goes
- [ARTICLE_CLASSIFICATION.md](ARTICLE_CLASSIFICATION.md) - what purpose the article serves
- [PUBLIC_SAFETY_RULES.md](PUBLIC_SAFETY_RULES.md) - what must remain out of the public repository

Together, these documents help turn the repository from a folder of Markdown files into an interconnected public knowledge system.

## Purpose

Knowledge relationships help maintainers, contributors, and AI assistants decide:

1. Which articles should be read before another article.
2. Which articles provide more detail after another article.
3. Which articles are related but not hierarchical.
4. Which troubleshooting, reference, or architecture documents support a topic.
5. How future AI retrieval and knowledge graph systems should connect content.

## Core Principle

Every article should be treated as part of a larger knowledge system.

An article should not be isolated. It should point readers and AI assistants toward prerequisite concepts, related topics, next steps, and supporting references when those connections improve understanding.

## Relationship Summary

| Relationship Type | Purpose | Example Use |
|---|---|---|
| Parent | Broader topic that contains or frames the article. | A saved search formula article may have Saved Searches as its parent. |
| Child | More specific article that expands on the current topic. | A Saved Searches overview may link to formulas, summaries, and criteria articles as children. |
| Prerequisite | Article the reader should understand first. | SuiteScript automation may require understanding records and transactions first. |
| Next Step | Recommended article after the current one. | After reading NetSuite navigation, the next step may be global search or records. |
| Related | Connected topic that is not directly hierarchical. | Inventory transfers may be related to locations and inventory valuation. |
| Troubleshooting | Diagnostic article commonly used with the topic. | User permissions may link to a troubleshooting article about record access. |
| Reference | Lookup article that supports the topic. | A how-to guide may link to a reference table of transaction statuses. |
| Architecture | Design or decision article related to the topic. | Integration setup may link to an integration architecture pattern. |

## Relationship Types

### Parent

A Parent relationship points to the broader topic that contains, frames, or organizes the current article.

Use Parent when:

- The current article is a more specific part of a broader concept.
- The broader article helps the reader understand context.
- The article belongs naturally under a module, process, or framework.

Example:

- Article: Saved Search Formulas
- Parent: Saved Searches

### Child

A Child relationship points to a more detailed article that expands on the current topic.

Use Child when:

- The current article is an overview.
- A more specific topic deserves its own article.
- The reader may want to go deeper after understanding the current article.

Example:

- Article: Saved Searches
- Children: Criteria, Results, Formulas, Summary Searches

### Prerequisite

A Prerequisite relationship points to an article that should be understood before the current one.

Use Prerequisite when:

- The current article assumes prior knowledge.
- A reader would struggle without understanding an earlier concept.
- An AI assistant should retrieve foundational context before answering an advanced question.

Example:

- Article: SuiteScript User Event Scripts
- Prerequisite: NetSuite Records and Transactions

### Next Step

A Next Step relationship points to the most useful article to read after the current one.

Use Next Step when:

- Articles are part of a learning path.
- A topic naturally progresses to a more advanced or practical article.
- The reader needs guided sequencing.

Example:

- Article: What Is NetSuite?
- Next Step: NetSuite Editions

### Related

A Related relationship points to a connected concept that is useful but not required.

Use Related when:

- Two topics often appear together.
- Understanding one topic gives useful context for another.
- The relationship is associative, not hierarchical.

Example:

- Article: Inventory Transfers
- Related: Locations, Inventory Adjustments, Inventory Valuation

### Troubleshooting

A Troubleshooting relationship points to diagnostic content commonly used with the current topic.

Use Troubleshooting when:

- The topic commonly produces errors or confusion.
- A support article helps diagnose common issues.
- Readers may need a path from concept to problem resolution.

Example:

- Article: Roles and Permissions
- Troubleshooting: User Cannot Access a Record

### Reference

A Reference relationship points to structured lookup material that supports the article.

Use Reference when:

- The current article depends on a list, table, glossary, or structured facts.
- The supporting material is useful but would interrupt the flow if embedded directly.
- The reader may need quick lookup while performing a task.

Example:

- Article: Sales Order Process Flow
- Reference: Common Sales Transaction Statuses

### Architecture

An Architecture relationship points to design, decision, or pattern documentation related to the article.

Use Architecture when:

- The article connects to a reusable design pattern.
- The topic involves tradeoffs across modules or systems.
- A solution architecture document provides broader implementation context.

Example:

- Article: REST Integration Concepts
- Architecture: Integration Ownership and System-of-Record Pattern

## Assignment Rules

1. Use relationships only when they help readers or AI assistants understand the content better.
2. Prefer a small number of meaningful relationships over many weak links.
3. Every overview article should usually have child or next-step relationships.
4. Every advanced article should usually have prerequisite relationships.
5. Troubleshooting articles should link back to the concepts they diagnose.
6. Reference articles should support task, concept, or troubleshooting articles without replacing them.
7. Architecture relationships should be reserved for design-level or decision-level context.
8. Related relationships should be useful, not decorative.
9. Do not create relationships to private company-specific documents from the public repository.

## Public-Safe Reminder

Knowledge relationships must follow the same public-safety rules as article content.

Do not link public articles to private company-specific files, screenshots, customer records, saved searches, workflow IDs, script IDs, internal procedures, pricing logic, manufacturing logic, or account-specific mappings.

Private overlays may link from private repositories back to this public repository, but the public repository should not expose private repository structure or private operating logic.

When in doubt, apply [PUBLIC_SAFETY_RULES.md](PUBLIC_SAFETY_RULES.md).
