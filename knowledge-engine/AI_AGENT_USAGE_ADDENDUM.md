# AI Agent Usage Addendum

## Purpose

This addendum explains how AI agents should use the Knowledge Engineering Framework when creating or updating public-safe NetSuite Intelligence Platform content.

The repository should be treated as a reasoning system, not only as a documentation library.

## Agent Workflow

When working in this repository, an AI agent should:

1. Identify the relevant knowledge cluster.
2. Review existing related articles before creating new content.
3. Create small, focused changes that are easy to review.
4. Prefer conceptual reasoning nodes over large troubleshooting documents.
5. Add or preserve metadata that supports semantic search and knowledge graphs.
6. Link articles together so retrieval systems can find related concepts.
7. Add benchmark questions when a cluster becomes mature enough to evaluate.
8. Keep all content public-safe.

## Public-Safe Boundaries

AI agents should avoid adding:

- company-specific operating procedures
- customer examples
- private account configuration
- screenshots of private systems
- credentials or account numbers
- pricing or negotiated rates
- custom fields from a specific account
- saved searches from a specific account
- workflows or scripts from a specific account
- proprietary implementation details

Those details belong in private repositories or internal knowledge sources.

## Reasoning Standard

A useful article should help an assistant answer:

> What knowledge would an experienced NetSuite consultant connect together to reason through this problem?

Good AI-ready content should connect:

- user question
- concept
- records
- related records
- process or lifecycle stage
- reasoning path
- troubleshooting path
- retrieval guidance
- escalation boundary

## Small-Commit Guidance

If a large article or edit is blocked or becomes hard to review, create a smaller conceptual node instead.

Preferred change pattern:

```text
small article or metadata improvement
  -> commit
  -> review
  -> expand later with another focused edit
```

This keeps the repository easier to review, safer to maintain, and more useful for RAG and knowledge graph retrieval.
