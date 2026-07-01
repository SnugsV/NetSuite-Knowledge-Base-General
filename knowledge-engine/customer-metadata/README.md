# Customer Metadata Framework

This framework defines exactly what customer-specific metadata must be collected before designing, troubleshooting, or generating any NetSuite solution. It prevents AI from making assumptions about a customer's environment.

## Purpose

Every customer implementation is different. The features they use, the customizations they have, the way they configure their forms — all affect how a solution should be designed. This framework ensures the AI collects the right evidence before offering any recommendation.

## Framework Documents

| Document | Purpose |
|---|---|
| [Metadata Reasoning](METADATA_REASONING.md) | Core methodology for metadata collection and confidence assessment |
| [Saved Search Metadata](saved-search-metadata.md) | Required metadata for Saved Search design |
| [Scripting Metadata](scripting-metadata.md) | Required metadata for SuiteScript, Workflow, RESTLet |
| [Configuration Metadata](configuration-metadata.md) | Required metadata for custom records, fields, forms, roles |
| [Integration Metadata](integration-metadata.md) | Required metadata for integrations, CSV imports, SuiteTalk |
| [Reporting Metadata](reporting-metadata.md) | Required metadata for workbooks, dashboards, KPIs |

## How It Integrates

```
Solution Architect selects a capability
       ↓
Metadata Framework validates what is known
       ↓
Missing metadata → Request from customer
       ↓
All required metadata collected → Route to AI Skill
       ↓
Missing metadata → Confidence is reduced
```

## Related Documents

- [Solution Architect](../solution-architect/README.md)
- [AI Skills](../ai-skills/README.md)
- [Customer Context](../customer-context/README.md)
- [Support Intelligence](../support-intelligence/README.md)