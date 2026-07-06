# Architecture Index

This document is the landing page for the core architecture documents in the NetSuite Knowledge Base General repository.

The purpose of this index is navigation only. It does not introduce new architecture concepts. It helps maintainers, contributors, and AI assistants understand which architecture document to read for each type of question.

## Purpose

Use this index to answer:

1. Which architecture documents exist?
2. What question does each document answer?
3. In what order should the documents be read?
4. Which document should guide a specific repository decision?

## Recommended Reading Order

| Order | Document | Question It Answers |
|---:|---|---|
| 1 | [PUBLIC_SAFETY_RULES.md](PUBLIC_SAFETY_RULES.md) | What is allowed in the public repository? |
| 2 | [KNOWLEDGE_DOMAINS.md](KNOWLEDGE_DOMAINS.md) | What is the content about? |
| 3 | [KNOWLEDGE_LEVELS.md](KNOWLEDGE_LEVELS.md) | How advanced is the content? |
| 4 | [ARTICLE_CLASSIFICATION.md](ARTICLE_CLASSIFICATION.md) | What kind of article is it? |
| 5 | [KNOWLEDGE_RELATIONSHIPS.md](KNOWLEDGE_RELATIONSHIPS.md) | How does this article connect to other knowledge? |
| 6 | [AI_RETRIEVAL_MODEL.md](AI_RETRIEVAL_MODEL.md) | How should AI systems retrieve and reason from the repository? |
| 7 | [ENTERPRISE_KNOWLEDGE_MODEL.md](ENTERPRISE_KNOWLEDGE_MODEL.md) | How does public knowledge relate to private enterprise knowledge? |

## Architecture Roles

### Public Safety Rules

Defines the boundary between public-safe knowledge and private organization-specific knowledge.

Read this before publishing, reviewing, or linking any content that could expose internal business operations.

### Knowledge Domains

Defines the major subject areas of the repository.

Use this when deciding where an article belongs or which business, platform, or technical area it covers.

### Knowledge Levels

Defines the maturity and depth of repository content.

Use this when deciding whether an article is beginner, operational, administrative, technical, architectural, or AI-reasoning oriented.

### Article Classification

Defines the purpose and format of an article.

Use this when deciding whether content should be a concept article, how-to guide, troubleshooting guide, reference article, decision framework, architecture pattern, or implementation guide.

### Knowledge Relationships

Defines how articles connect to each other.

Use this when adding parent, child, prerequisite, next-step, related, troubleshooting, reference, or architecture links.

### AI Retrieval Model

Defines how AI systems should retrieve and reason from public repository content.

Use this when designing AI-friendly documentation, retrieval workflows, semantic search behavior, or source-grounded answers.

### Enterprise Knowledge Model

Defines how the public repository relates to private enterprise repositories.

Use this when deciding whether content belongs in the public knowledge engine or in a private company-specific overlay.

## Contributor Guidance

Before adding or changing public documentation, contributors should ask:

1. Is this public-safe?
2. What domain does it belong to?
3. What knowledge level is it written for?
4. What article type is it?
5. What related articles should it connect to?
6. Will AI systems be able to retrieve and use it correctly?
7. Does any part of this belong in a private repository instead?

## AI Assistant Guidance

AI assistants using this repository should treat the architecture documents as operating rules.

When answering questions from repository content, an AI assistant should:

- Respect public/private boundaries.
- Retrieve content by domain, level, type, and relationship.
- Prefer foundational concepts before advanced guidance when needed.
- Avoid inventing private organization-specific details.
- Identify missing private context when a question cannot be answered from public knowledge alone.

## Public-Safe Reminder

This index links only to public repository architecture documents.

Do not add links here to private repositories, private company files, screenshots, saved searches, scripts, workflows, pricing logic, manufacturing logic, customer documentation, vendor documentation, or internal procedures.

When in doubt, apply [PUBLIC_SAFETY_RULES.md](PUBLIC_SAFETY_RULES.md).
