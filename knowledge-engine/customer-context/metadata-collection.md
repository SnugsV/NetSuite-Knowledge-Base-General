# Metadata Collection

## Purpose

Metadata is the evidence that confirms or eliminates hypotheses. Without metadata, troubleshooting is guesswork. This document defines what metadata to request, when to request it, and why it matters.

## Metadata Request Decision Tree

```
Is the problem related to a specific transaction?
  ├── Yes → Request the transaction record and related documents
  │
  └── No → Is it related to configuration?
              ├── Yes → Request screenshots of configuration pages
              │
              └── No → Is it related to customization?
                          ├── Yes → Request script exports or workflow details
                          │
                          └── No → Request saved searches or reports
```

## What to Request and Why

| Metadata | Why Request It | When to Request |
|---|---|---|
| **Transaction record** | Shows exact state of the document — status, dates, quantities, user assignments | Every transaction-related issue |
| **Related records** | Shows upstream/downstream documents affecting the transaction | When transaction is not behaving as expected |
| **Saved Search export** | Shows data from the customer's perspective — useful for comparing expectations to reality | For data or reporting issues |
| **Custom field definitions** | Shows validation rules, mandatory status, display logic | When a transaction won't save or submit |
| **Script deployment** | Shows which scripts are deployed on which records | For automation or integration issues |
| **Workflow detail** | Shows workflow states, transitions, and actions | When a workflow is stuck or not triggering |
| **Audit trail** | Shows who did what and when | When unauthorized changes are suspected |
| **Error log** | Shows system errors, script errors, and integration failures | When there is an error message |
| **Configuration screenshot** | Provides visual confirmation of settings | When verifying feature enablement or configuration |
| **Role permissions** | Shows what a user can see and do | For access or visibility issues |
| **Sample transactions** | Provides realistic data for testing | When reproducing an issue in a sandbox |

## Requesting Metadata Effectively

### Be Specific

Instead of "Send me the error," request:
"Please navigate to Customization > Scripting > Script Deployments and filter by the sales order record type. Capture a screenshot of the list showing script name, status, and deployment date."

### Explain Why

Explain why the metadata is needed:
"I'm requesting the audit trail for this transaction so I can see which user made the last change and when."

### Request in Priority Order

Request the most important metadata first. Do not overwhelm the customer with every request at once.

| Priority | What to Request First |
|---|---|
| 1 | Transaction record (if applicable) |
| 2 | Error message and error log |
| 3 | Relevant configuration screenshots |
| 4 | Related custom field or script information |
| 5 | Audit trail |

## Minimum Viable Metadata

When the customer is unable or unwilling to provide extensive metadata, request the minimum:

- **For transaction issues**: The transaction number and the exact error message
- **For configuration issues**: A screenshot of the relevant settings page
- **For customization issues**: The script name and deployment information
- **For performance issues**: Time of occurrence, affected records, and any error messages

## Metadata Validation

Before accepting metadata as sufficient:

- [ ] Does the metadata cover the affected transaction/record/configuration?
- [ ] Is the metadata from the correct environment (production vs. sandbox)?
- [ ] Is the metadata recent enough to be relevant?
- [ ] Does the metadata contradict or confirm the stated problem?

## Related Documents

- [Customizations](customizations.md)
- [NetSuite Configuration](netsuite-configuration.md)
- [Problem Classification](problem-classification.md)

## Oracle References

- [Oracle NetSuite Help Center: Audit Trail](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Saved Search Export](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)