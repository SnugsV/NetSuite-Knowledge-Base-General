# ERP Intelligence Knowledge Model

## Purpose

This document defines the layered knowledge model for the NetSuite Intelligence Platform.

The repository is evolving from a collection of documentation into a public-safe ERP knowledge system. The goal is to capture concepts, relationships, workflows, troubleshooting paths, and reasoning patterns so future articles work together as connected consultant memory.

## Guiding Question

Every knowledge domain should be built around this question:

> What knowledge is needed to reason like an experienced NetSuite consultant?

This is different from simply asking what article should be written next.

## The Six-Layer Model

Each major product or knowledge domain should eventually contain six layers:

```text
Layer 1: Foundation
Layer 2: NetSuite Integration
Layer 3: Knowledge Clusters
Layer 4: Troubleshooting
Layer 5: Reference
Layer 6: Reasoning
```

These layers do not need to be built all at once. Build one platform, one cluster, and one small article at a time.

## Layer 1: Foundation

Foundation articles explain the product, concept, or domain.

Typical articles:

- Product facts
- Business purpose
- Terminology
- Platform overview
- Source guide
- Concept glossary

Foundation answers:

- What is this?
- Why does it exist?
- Who uses it?
- What business problem does it solve?
- What are the basic terms?

## Layer 2: NetSuite Integration

NetSuite Integration articles explain how the product or domain touches NetSuite.

Typical articles:

- NetSuite touchpoints
- Record relationships
- Data flow
- Integration architecture
- Sync direction
- Transaction lifecycle impact

NetSuite Integration answers:

- Which NetSuite records are involved?
- Which transactions are affected?
- What data moves between systems?
- What happens inside NetSuite?
- What happens outside NetSuite?
- Where can mismatches occur?

## Layer 3: Knowledge Clusters

Knowledge clusters are connected article groups around a specific business capability.

Examples:

| Platform | Cluster Examples |
|---|---|
| Avalara | Address, Exemptions, Transactions, Returns, Compliance |
| SPS Commerce | Purchase Orders, Acknowledgments, ASNs, Invoices, Trading Partners |
| Pacejet | Rating, Packing, Shipping, Tracking, Carrier Errors |
| Shopify | Orders, Customers, Fulfillment, Refunds, Product Sync |
| Celigo | Flows, Mappings, Errors, Retries, Monitoring |

Clusters answer:

- What related concepts belong together?
- Which employee questions belong to this domain?
- What records and workflows are connected?
- What should be retrieved together?

## Layer 4: Troubleshooting

Troubleshooting articles explain symptoms, likely causes, first checks, and escalation paths.

Typical articles:

- Why did this not calculate?
- Why did this not sync?
- Why did this fail?
- Error message guides
- Decision guides
- Root cause analysis guides

Troubleshooting answers:

- What symptom is visible?
- What are the most likely causes?
- What should be checked first?
- Which records are involved?
- Is this likely a NetSuite issue, external platform issue, data issue, timing issue, setup issue, or user process issue?
- What information is needed before escalation?

## Layer 5: Reference

Reference articles provide stable lookup information.

Typical articles:

- FAQs
- Glossaries
- Best practices
- Common scenarios
- Public source indexes
- Terminology maps
- Record or object indexes

Reference answers:

- What does this term mean?
- What are common scenarios?
- Which public source supports this?
- Which article should be read next?
- What best practices apply generally?

## Layer 6: Reasoning

Reasoning articles explain how to think through a domain.

Typical articles:

- Decision trees
- Consultant workflows
- Diagnostic paths
- Root cause frameworks
- When to check what
- How to separate similar issues

Reasoning answers:

- What should be checked first?
- What assumptions should be avoided?
- What records should be connected?
- What evidence is needed?
- When is internal verification needed?
- What public-safe answer can be provided?

Reasoning is what turns documentation into consultant memory.

## Coverage Model

Do not measure maturity by file count alone. Measure by knowledge coverage.

Example:

| Platform | Domain | Foundation | Integration | Clusters | Troubleshooting | Reference | Reasoning |
|---|---|---:|---:|---:|---:|---:|---:|
| Avalara | Address | 100% | 100% | 100% | 100% | 80% | 80% |
| Avalara | Exemptions | 20% | 20% | 10% | 0% | 0% | 0% |
| Avalara | Transactions | 0% | 0% | 0% | 0% | 0% | 0% |
| SPS Commerce | Foundation | 0% | 0% | 0% | 0% | 0% | 0% |
| Pacejet | Foundation | 0% | 0% | 0% | 0% | 0% | 0% |

Coverage should be judged by whether real employee questions can be answered accurately.

## Article Type Mapping

| Article Type | Primary Layer | Purpose |
|---|---|---|
| Platform Overview | Foundation | Explain what the product is |
| Product Facts | Foundation | Capture stable public facts |
| Terminology | Foundation / Reference | Define terms |
| NetSuite Touchpoints | NetSuite Integration | Identify NetSuite records and workflows |
| Record Relationships | NetSuite Integration | Explain connected records |
| Data Flow | NetSuite Integration | Explain movement of data |
| Cluster Foundation | Knowledge Clusters | Introduce a capability area |
| Scenario Guide | Knowledge Clusters / Troubleshooting | Explain real situations |
| Troubleshooting Guide | Troubleshooting | Diagnose symptoms |
| Decision Tree | Reasoning | Guide diagnostic thinking |
| FAQ | Reference | Answer common questions |
| Best Practices | Reference / Reasoning | Recommend general approaches |

## Product Build Pattern

When starting a new platform, use this sequence:

1. Build enough foundation to understand the product.
2. Identify NetSuite touchpoints.
3. Map record relationships.
4. Map data flow.
5. Pick one high-value knowledge cluster.
6. Build the cluster to consultant quality.
7. Add troubleshooting and reasoning.
8. Repeat the pattern for the next cluster.

Do not start every cluster at once. A complete cluster is more valuable than many shallow stubs.

## Example: Avalara Build Pattern

Recommended sequence:

1. Foundation
   - Product Facts
   - Business Purpose
   - Terminology
2. NetSuite Integration
   - Touchpoints
   - Record Relationships
   - Data Flow
3. Address Cluster
   - Address Validation
   - Which Address Does Avalara Use?
   - Jurisdictions
   - Geolocation
   - Address Troubleshooting
4. Exemption Cluster
   - Exemption Certificates
   - Customer Exemptions
   - Item Taxability
   - Why Is Customer Tax Exempt?
   - Exemption Troubleshooting
   - Common Exemption Scenarios
5. Transaction Cluster
   - Sales Orders
   - Invoices
   - Cash Sales
   - Credit Memos
   - Transaction Lifecycle
6. Additional clusters
   - Returns
   - Compliance
   - Connector Troubleshooting
   - Error Messages
   - Best Practices

## Public-Safe Boundary

The public repository may include:

- NetSuite concepts
- ERP education
- public product information
- vendor-neutral explanations
- AI reasoning models
- generic troubleshooting
- public business workflows
- platform overviews

Company-specific setup, proprietary process details, customer-specific data, screenshots, scripts, and configuration decisions belong outside the public repository.

## Consultant Memory Standard

An article or cluster reaches consultant-memory quality when it can help a reader:

1. Understand the concept.
2. Identify the relevant records.
3. Explain the business process.
4. Recognize common symptoms.
5. Suggest first checks.
6. Separate likely causes.
7. Avoid unsafe assumptions.
8. Know when verification is needed.
9. Link to related knowledge.
10. Provide a public-safe answer.

## Definition of a Complete Cluster

A knowledge cluster is complete when it contains:

- foundation context
- key terminology
- record relationships
- process flow
- common employee questions
- troubleshooting guidance
- related article links
- public source references
- reasoning guidance
- clear public/private boundary

A cluster does not need to be large to be complete. It needs to be useful, connected, and reliable.

## Contributor Guidance

When creating a new article, ask:

1. Which layer does this article belong to?
2. Which cluster does it strengthen?
3. Which employee question does it answer?
4. Which records or systems are involved?
5. What should be retrieved with it?
6. What assumptions should be avoided?
7. Is every detail public-safe?
8. Is the article original and source-informed?

## Related Documents

- [AI Knowledge Metadata](AI_KNOWLEDGE_METADATA.md)
- [Documentation Standards](DOCUMENTATION_STANDARDS.md)
- [AI Standards](AI_STANDARDS.md)
- [Review Checklist](REVIEW_CHECKLIST.md)
- [Knowledge Cluster Article Template](../templates/KNOWLEDGE_CLUSTER_TEMPLATE.md)
