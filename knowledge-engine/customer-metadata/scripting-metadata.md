# Scripting Metadata

## Purpose

Defines exactly what metadata must be collected before designing, modifying, or troubleshooting SuiteScript, Workflows, or RESTlets. Script behavior is heavily dependent on deployment configuration, governance limits, and existing customizations.

## Required Metadata

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Existing scripts on the record type** | Multiple scripts on the same record type can conflict or execute in unexpected order | Request script deployment list filtered by record type |
| **Script type required** | User Event, Client, Scheduled, Map/Reduce, RESTlet — each has different use cases and limitations | Ask: "What should trigger this script?" |
| **Deployment configuration** | Status (active/inactive), audience, event types, and deployment filters | Request deployment record details |
| **Script governance limits** | Maximum governance units per script, per account — determines script complexity | Check account-level script governance settings |
| **NetSuite release version** | Script APIs change between releases — code that works in one release may not work in the next | Ask: "What NetSuite release version are you on?" |

## Optional Metadata

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Existing script names and IDs** | Identifies what has already been implemented | Request script list export |
| **Log level and execution logs** | Shows current script behavior and errors | Request execution log export |
| **Bundle scripts** | Bundles may deploy scripts that conflict with custom scripts | Review installed bundles |
| **Error history** | Identifies recurring script failures | Request error log export for the last 30 days |
| **Map/Reduce concurrency** | Determines how Map/Reduce scripts should be configured | Check account Map/Reduce settings |

## Workflow-Specific Metadata

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Existing workflows on the record type** | Multiple workflows on the same record can interact in unexpected ways | Request workflow deployment list |
| **Workflow states and transitions** | Required to understand current behavior before modifying | Request workflow definition export |
| **Approval chain configuration** | Determines how approval routing works | Review workflow approval step configuration |
| **Workflow email templates** | Email templates used in workflow notifications | Request email template list |

## RESTlet-Specific Metadata

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **External system details** | Determines authentication method, data format, and expected response | Ask: "What system is calling this RESTlet?" |
| **API authentication method** | OAuth, token-based, or signature-based | Confirm authentication configuration |
| **Request and response format** | JSON, XML, or custom format | Request sample request/response from the external system |
| **Rate limiting requirements** | Determines how many requests the RESTlet should handle | Ask: "How many requests per minute/hour?" |

## Validation Checklist

- [ ] Script type confirmed for the requirement
- [ ] Existing scripts on the record type reviewed
- [ ] Governance limits understood
- [ ] Deployment configuration confirmed
- [ ] Workflow interactions identified (if applicable)
- [ ] Error logs reviewed for existing scripts
- [ ] External system details confirmed (for RESTlets)

## Common Metadata Gaps

| Gap | Impact | Recovery |
|---|---|---|
| Existing scripts not reviewed | Custom script may conflict with existing automation | Request script deployment list |
| Governance limits unknown | Script may hit governance limits in production | Check script governance settings |
| Workflow interactions missed | Workflow and script may process the same record differently | Review all automations on the record type |
| Release compatibility not checked | Script may use deprecated APIs | Check NetSuite release notes for API changes |

## Confidence Impact

| Metadata Collected | Confidence |
|---|---|
| All required + existing scripts reviewed | High |
| All required + some optional | Medium |
| Governance limits unknown + existing scripts not reviewed | Low |
| Required metadata missing | Unknown — do not proceed |

## Related Documents

- [METADATA_REASONING.md](METADATA_REASONING.md)
- [Customer Context: Customizations](../customer-context/customizations.md)