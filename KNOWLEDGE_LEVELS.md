# Knowledge Levels

This document defines the standard knowledge maturity levels for the NetSuite Knowledge Base General repository.

Knowledge levels describe how deep an article goes. They complement [KNOWLEDGE_DOMAINS.md](KNOWLEDGE_DOMAINS.md), which describes what an article is about.

Together, domains and levels create a simple classification model:

- Domain = subject area
- Level = depth and audience

## Purpose

Knowledge levels help maintainers, contributors, and AI assistants decide:

1. Who the article is written for.
2. What background knowledge the reader needs.
3. How detailed the article should be.
4. Whether the article should explain, guide, troubleshoot, design, or reason.
5. Which lower-level articles should be referenced as prerequisites.

## Core Principle

Each article should have one primary knowledge level.

An article may reference lower or higher levels, but it should not try to serve every audience at once. Beginner articles should stay beginner-friendly. Advanced architecture articles should not be forced to explain every basic term inline.

## Level Summary

| Level | Name | Primary Audience | Goal |
|---:|---|---|---|
| 100 | Foundations | Beginners, new users, students, AI assistants needing definitions | Understand terminology, navigation, records, and core concepts. |
| 200 | Functional Operations | Business users, power users, department leads | Perform day-to-day business processes confidently. |
| 300 | Administration | NetSuite administrators, implementation teams, auditors | Configure, secure, maintain, and govern the platform. |
| 400 | Technical Implementation | Developers, technical consultants, integration teams | Build, customize, automate, integrate, and troubleshoot technical behavior. |
| 500 | Solution Architecture | Consultants, solution architects, project teams, business leaders | Design cross-functional solutions and choose the right NetSuite capabilities. |
| 600 | AI Reasoning & Knowledge Engineering | AI agents, maintainers, expert practitioners, enterprise knowledge teams | Apply structured reasoning across domains, validate answers, and support AI retrieval. |

## Level 100 - Foundations

Use Level 100 for introductory explanations.

Typical content:

- What a concept means
- Where a feature fits in NetSuite
- Basic terminology
- Simple record or transaction explanations
- Navigation and interface orientation
- Glossary-style articles

The article should assume little or no prior NetSuite experience.

Good Level 100 questions:

- What is NetSuite?
- What is a customer record?
- What is a role?
- What is a sales order?
- What is a saved search?

## Level 200 - Functional Operations

Use Level 200 for everyday business process guidance.

Typical content:

- How business users complete routine work
- Standard process flow
- Common transaction lifecycle explanations
- Operational handoffs between departments
- Practical examples without private company details

The article should assume the reader understands basic NetSuite terminology.

Good Level 200 questions:

- How does order fulfillment generally work?
- How does procure-to-pay flow through NetSuite?
- How do inventory transfers affect stock levels?
- How do users monitor open transactions?

## Level 300 - Administration

Use Level 300 for configuration, governance, and account management.

Typical content:

- Feature setup
- Users, roles, and permissions
- Preferences and configuration
- Forms and centers
- Authentication and security controls
- Sandbox and release preview guidance
- Administrative review checklists

The article should assume the reader understands both NetSuite basics and the relevant business process.

Good Level 300 questions:

- How should roles and permissions be reviewed?
- What should administrators check before enabling a feature?
- How do system notes support auditability?
- How should release preview be used?

## Level 400 - Technical Implementation

Use Level 400 for development, integration, automation, and technical troubleshooting.

Typical content:

- SuiteScript concepts
- SuiteTalk REST and SOAP concepts
- Integration design basics
- Workflow vs script tradeoffs
- Custom records and fields
- Error handling patterns
- Technical deployment considerations

The article should assume the reader understands the relevant process and basic administration concepts.

Good Level 400 questions:

- When should SuiteScript be used instead of workflow?
- How should integrations identify records?
- What are common API error patterns?
- How should scheduled automation be designed?

## Level 500 - Solution Architecture

Use Level 500 for cross-functional design and implementation decisions.

Typical content:

- Discovery questions
- Design tradeoffs
- Capability selection
- Phased rollout planning
- Cross-module process design
- Risk and dependency mapping
- Build vs configure vs integrate decisions

The article should assume the reader understands the business process, administrative options, and technical implementation choices.

Good Level 500 questions:

- Should this process be solved with configuration, workflow, script, or integration?
- How should an order-to-cash solution be designed across systems?
- What dependencies should be reviewed before implementing manufacturing?
- How should a reporting strategy be planned across departments?

## Level 600 - AI Reasoning & Knowledge Engineering

Use Level 600 for AI-oriented reasoning, retrieval, validation, and knowledge architecture.

Typical content:

- AI retrieval patterns
- Knowledge graph relationships
- Root cause reasoning models
- Diagnostic frameworks
- Prompt and agent guidance
- Validation and benchmark frameworks
- Public/private knowledge separation
- Enterprise knowledge overlay models

The article should assume the reader or AI system is using the repository to reason across multiple domains.

Good Level 600 questions:

- How should an AI assistant classify a NetSuite issue?
- What evidence should be gathered before recommending a solution?
- How should public knowledge connect to private company overlays?
- How should AI-generated NetSuite guidance be validated?

## Progression Model

Knowledge should generally progress in this order:

```text
100 Foundations
  -> 200 Functional Operations
    -> 300 Administration
      -> 400 Technical Implementation
        -> 500 Solution Architecture
          -> 600 AI Reasoning & Knowledge Engineering
```

Not every reader needs every level. A warehouse user may only need Levels 100 and 200. A developer may need Levels 100 through 400. An AI agent or solution architect may need all six.

## Article Assignment Rules

1. Assign the level based on the article's primary purpose, not the most advanced term mentioned.
2. If an article explains what something is, it is usually Level 100.
3. If an article explains how business users perform work, it is usually Level 200.
4. If an article explains configuration or governance, it is usually Level 300.
5. If an article explains customization, scripting, APIs, or integration behavior, it is usually Level 400.
6. If an article compares options or designs a solution, it is usually Level 500.
7. If an article supports AI retrieval, reasoning, validation, or knowledge architecture, it is usually Level 600.
8. Do not make beginner articles overly complex just to cover advanced exceptions.
9. Do not include private company-specific details at any level.

## Metadata Recommendation

Future articles should include knowledge level metadata when structured front matter is adopted.

Example:

```yaml
primary_domain: Administration & Security
related_domains:
  - Governance & Public Safety
knowledge_level: 300
article_type: guide
public_safety_review: required
```

Until formal metadata is adopted, reviewers should still classify each article by domain and level during review.

## Public-Safe Reminder

Higher knowledge levels do not allow private information.

Level 400, 500, and 600 articles may discuss advanced ideas, but they must remain generic and reusable. Do not include private screenshots, internal IDs, saved search formulas tied to private operations, SuiteScript source code from a private company, credentials, account URLs, pricing logic, manufacturing logic, customer-specific mappings, or internal procedures.

When in doubt, apply [PUBLIC_SAFETY_RULES.md](PUBLIC_SAFETY_RULES.md).
