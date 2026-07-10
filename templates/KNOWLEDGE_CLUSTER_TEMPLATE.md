# Knowledge Cluster Article Template

Use this template for consultant-grade knowledge articles that are designed to help an AI assistant reason through NetSuite ecosystem questions.

This template is intentionally different from a traditional documentation template. It is optimized for:

- RAG retrieval
- employee question answering
- record relationship mapping
- troubleshooting reasoning
- knowledge graph construction
- public-safe ecosystem intelligence

For general learning articles, use the standard article template. For product intelligence, integration intelligence, decision guides, and troubleshooting articles, use this template.

---

title:
platform:
cluster:
knowledge_type:
primary_records:
  - 
related_records:
  - 
related_articles:
  - 
keywords:
  - 
difficulty:
last_verified:
public_sources:
  - 
reasoning_prerequisites:
  - 
employee_questions_answered:
  - 
---

# Article Title

## Quick Summary

Write one to three sentences that explain the practical purpose of this article.

The quick summary should answer:

- What is this topic?
- Why does it matter?
- What kind of employee question should this help answer?

## Business Purpose

Explain the business problem this knowledge solves.

Focus on why a company cares about this topic, not just how the software behaves.

Good questions to answer:

- What business process depends on this?
- What risk does this reduce?
- Which teams are affected?
- What happens when this is misunderstood?

## Core Concepts

Define the essential concepts needed to understand the topic.

Keep definitions original, concise, and NetSuite-centered. Do not copy vendor documentation.

Recommended format:

| Concept | Meaning | Why It Matters |
|---|---|---|
| Example concept | Plain-language explanation | Business or system impact |

## NetSuite Perspective

Explain how NetSuite usually represents, stores, triggers, or exposes this concept.

Include relevant record types, transaction types, fields in general terms, roles, permissions, or process touchpoints.

Do not include private company custom fields, saved searches, workflows, scripts, screenshots, or proprietary setup details.

## External Platform Perspective

Explain how the external platform or vendor system thinks about the same topic.

Examples:

- Avalara tax logic
- SPS Commerce EDI documents
- Pacejet shipment rating and execution
- Shopify orders and fulfillment state
- Celigo integration flows

Keep this public-safe and source-informed.

## Record Relationships

Describe the records or objects that interact with this topic.

Recommended format:

| Record or Object | Role in the Process | Common Failure Point |
|---|---|---|
| Customer | Example role | Example failure |

## Data Flow

Explain how information moves between systems or records.

Use a simple step sequence when possible.

Example:

1. User creates or updates a record.
2. NetSuite stores or exposes relevant data.
3. External platform receives or evaluates the data.
4. Result is returned, stored, displayed, or used by a downstream process.

## Decision Logic

Explain how an experienced consultant would reason through the topic.

This is one of the most important sections for GPT behavior.

Use condition-based logic where helpful:

```text
If X is true, check Y.
If Y is missing, inspect Z.
If Z is valid, the issue is likely outside NetSuite.
```

## Common Employee Questions

List realistic employee questions this article should help answer.

Use plain language rather than only technical wording.

Examples:

- Why did this transaction behave differently than expected?
- Which record should I check first?
- Is this a NetSuite issue or an external platform issue?
- What information do I need before escalating?

## Troubleshooting Notes

List common symptoms, likely causes, and first checks.

Recommended format:

| Symptom | Likely Causes | First Checks |
|---|---|---|
| Example symptom | Example causes | Example checks |

## Best Practices

Provide public-safe best practices that would help a general NetSuite user, admin, or consultant.

Avoid company-specific SOPs.

Good best practices are:

- actionable
- generalizable
- non-proprietary
- tied to business outcomes

## AI Reasoning Guidance

Explain how a GPT should use this article when answering employee questions.

Recommended prompts to answer:

- What should the assistant ask first?
- What should the assistant not assume?
- What records or concepts should the assistant connect?
- When should the assistant say the issue needs internal verification?

## Related Articles

Add links to related knowledge articles.

Use relative paths where possible.

- [Related article](RELATED_ARTICLE.md)

## Public Sources

List public sources used to verify the article.

Do not include private repositories, internal notes, customer data, custom screenshots, or Holland Bar Stool configuration details in the public repository.

- Public source name or URL

## Public-Safety Review

Before committing, verify that the article does not contain:

- Holland Bar Stool SOPs
- custom fields
- saved searches
- workflows
- SuiteScripts
- pricing logic
- manufacturing logic
- internal prompts
- screenshots
- customer-specific documentation
- tax configuration decisions
- nexus decisions

If any of those are needed, put them in a private repository instead.
