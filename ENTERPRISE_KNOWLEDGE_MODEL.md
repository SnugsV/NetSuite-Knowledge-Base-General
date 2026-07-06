# Enterprise Knowledge Model

This document defines the initial enterprise knowledge model for the NetSuite Knowledge Base General repository.

The goal is to clarify how this public repository relates to private enterprise knowledge repositories without exposing private company-specific information.

This first version intentionally stays small. It defines the purpose, scope, core principle, and high-level repository roles only. More detailed guidance for overlays, retrieval orchestration, access control, synchronization, and governance should be added in later micro-edits.

## Related Architecture Documents

This model builds on the repository's core architecture documents:

- [PUBLIC_SAFETY_RULES.md](PUBLIC_SAFETY_RULES.md) - what must remain out of the public repository
- [KNOWLEDGE_DOMAINS.md](KNOWLEDGE_DOMAINS.md) - what public content is about
- [KNOWLEDGE_LEVELS.md](KNOWLEDGE_LEVELS.md) - how deep public content goes
- [ARTICLE_CLASSIFICATION.md](ARTICLE_CLASSIFICATION.md) - what purpose public content serves
- [KNOWLEDGE_RELATIONSHIPS.md](KNOWLEDGE_RELATIONSHIPS.md) - how public articles connect
- [AI_RETRIEVAL_MODEL.md](AI_RETRIEVAL_MODEL.md) - how AI systems should retrieve public knowledge

## Purpose

The enterprise knowledge model helps maintainers, contributors, and AI assistants understand:

1. What belongs in the public knowledge repository.
2. What belongs in private enterprise repositories.
3. How public and private knowledge should complement each other.
4. How AI systems should reason across general knowledge and private overlays without mixing boundaries.
5. How the repository can remain useful to the public while supporting private enterprise use cases.

## Scope

This document applies to the public NetSuite Knowledge Base General repository and its relationship to future or existing private repositories.

It does not define the exact structure of any private repository. Private repositories should define their own structure, permissions, governance rules, and access controls.

## Core Principle

The public repository explains how NetSuite works.

Private repositories explain how a specific organization uses NetSuite.

This distinction protects private business knowledge while allowing the public repository to remain broadly useful, community-friendly, and AI-ready.

## Repository Roles

### Public Repository

The public repository should contain general, reusable, public-safe knowledge.

Appropriate public content includes:

- General NetSuite concepts
- ERP education
- Generic implementation guidance
- Public-safe troubleshooting patterns
- Best practices that apply across organizations
- AI reasoning frameworks
- Documentation standards
- Public knowledge architecture
- General integration concepts
- General reporting and saved search education

The public repository should be useful to administrators, consultants, developers, students, business users, and AI assistants without revealing how any specific private organization operates.

### Private Enterprise Repositories

Private repositories should contain organization-specific knowledge.

Private content may include:

- Internal SOPs
- Saved searches
- Custom fields
- Workflows
- SuiteScripts
- Account-specific configuration
- Manufacturing logic
- Pricing logic
- Customer-specific documentation
- Vendor-specific documentation
- Internal screenshots
- Internal AI prompts
- Integration mappings
- Security and access rules
- Support procedures

Private repositories may use the public repository as a foundation, but they should never push private implementation details back into the public repository.

## Public-to-Private Relationship

The public repository should act as the general knowledge engine.

Private repositories should act as enterprise overlays.

In practice:

- Public knowledge teaches the concept.
- Private knowledge applies the concept to a specific organization.
- Public knowledge defines reusable patterns.
- Private knowledge defines approved internal procedures.
- Public knowledge supports broad AI reasoning.
- Private knowledge supplies authorized private context.

## AI Usage Principle

An AI assistant should use public knowledge for general NetSuite reasoning and private knowledge for organization-specific answers.

If private context is required but unavailable, the assistant should not guess. It should identify the missing private context and explain what information is needed.

## Public-Safe Reminder

Do not include private company names, internal identifiers, screenshots, account-specific mappings, saved searches, custom field IDs, workflow IDs, script IDs, credentials, pricing logic, manufacturing logic, or internal procedures in this public repository.

Private repositories may link to public concepts, but this public repository should not expose private repository structure, private file names, private business logic, or private operating procedures.

When in doubt, apply [PUBLIC_SAFETY_RULES.md](PUBLIC_SAFETY_RULES.md).
