# AI Retrieval Model

This document defines the initial AI retrieval model for the NetSuite Knowledge Base General repository.

The goal is to make the repository useful not only for human readers, but also for AI assistants, retrieval systems, and future knowledge graph tooling.

This first version intentionally stays small. It defines the purpose, scope, and core retrieval principles only. More detailed guidance for chunking, metadata, citations, retrieval workflows, and validation should be added in later micro-edits.

## Related Architecture Documents

This model builds on the repository's core architecture documents:

- [PUBLIC_SAFETY_RULES.md](PUBLIC_SAFETY_RULES.md) - what must remain out of the public repository
- [KNOWLEDGE_DOMAINS.md](KNOWLEDGE_DOMAINS.md) - what the article is about
- [KNOWLEDGE_LEVELS.md](KNOWLEDGE_LEVELS.md) - how deep the article goes
- [ARTICLE_CLASSIFICATION.md](ARTICLE_CLASSIFICATION.md) - what purpose the article serves
- [KNOWLEDGE_RELATIONSHIPS.md](KNOWLEDGE_RELATIONSHIPS.md) - how articles connect

## Purpose

The AI retrieval model helps maintainers and AI systems decide:

1. Which content should be retrieved for a question.
2. Which articles should be treated as foundational context.
3. Which articles should be treated as task, troubleshooting, architecture, or reference material.
4. How public knowledge should remain separate from private company-specific overlays.
5. How future AI assistants should reason from repository content without inventing unsupported details.

## Scope

This model applies to the public NetSuite Knowledge Base General repository.

It is intended for:

- AI assistants answering NetSuite questions
- Retrieval-augmented generation systems
- Future semantic search tooling
- Knowledge graph development
- Contributor and maintainer guidance
- Public documentation quality review

It does not define private company-specific retrieval rules. Private repositories may use this public repository as a foundation, but private retrieval models must add their own access controls, data boundaries, and company-specific rules.

## Core Retrieval Principles

### 1. Retrieve public knowledge first

AI systems should use this repository for general NetSuite concepts, ERP education, generic implementation guidance, troubleshooting patterns, and public-safe reasoning frameworks.

Company-specific procedures, account configuration, saved searches, scripts, screenshots, mappings, pricing, manufacturing logic, and internal operations must come from private repositories only.

### 2. Respect the public/private boundary

The public repository should never imply that it knows how a specific private organization operates.

If an answer requires private details, the AI assistant should identify the missing private context instead of guessing.

### 3. Prefer structured context over isolated snippets

AI retrieval should consider an article's domain, knowledge level, article type, and relationships when selecting context.

A strong retrieval result should answer:

- What domain is this about?
- What level of depth is needed?
- What type of answer is expected?
- What prerequisite or related articles should also be considered?

### 4. Retrieve foundational concepts before advanced guidance

When a question involves advanced configuration, automation, integrations, troubleshooting, or solution architecture, AI systems should retrieve foundational articles first when needed.

Advanced answers should not skip core NetSuite concepts if those concepts are necessary to avoid confusion.

### 5. Use relationships to improve context

Knowledge relationships should help retrieval systems find parent, child, prerequisite, next-step, related, troubleshooting, reference, and architecture documents.

Articles should become more useful over time as relationships are added.

### 6. Favor source-grounded answers

AI systems should answer from repository content when possible and avoid inventing unsupported claims.

If the repository does not contain enough information, the assistant should say what is missing and recommend the next source or document needed.

### 7. Keep retrieval generic and reusable

Public retrieval should produce answers that are useful across many organizations.

Do not tailor public retrieval behavior to one private company, one NetSuite account, one customer, one workflow, one saved search, or one implementation.

## Future Expansion

Later micro-edits should add focused sections for:

- Chunking guidance
- Metadata expectations
- Citation and source-grounding rules
- Retrieval priority rules
- Semantic search guidance
- Knowledge graph integration
- Public/private overlay retrieval
- AI validation and benchmark expectations

Each topic should be added as its own small, reviewable commit.

## Public-Safe Reminder

AI retrieval must follow [PUBLIC_SAFETY_RULES.md](PUBLIC_SAFETY_RULES.md).

Do not retrieve, expose, summarize, or infer private company-specific information from this public repository. If private context is required, the AI assistant should request or retrieve it only from an authorized private source.
