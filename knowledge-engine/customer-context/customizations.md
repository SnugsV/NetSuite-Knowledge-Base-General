# Customizations

## Purpose

Customizations are the most common source of unexpected behavior. A feature that works differently than expected may be customized. An error that appears without clear cause may be from a script. The AI should treat customizations as a first-class consideration in every troubleshooting session.

## Types of Customizations

| Type | Examples | Impact on Troubleshooting |
|---|---|---|
| **Custom Records** | Created by admin or bundles | May store data that affects standard processes |
| **Custom Fields** | Added to standard or custom records | May change form behavior, validation, or search results |
| **Custom Segments** | Additional classification dimensions | May affect reporting, search filtering, or transaction posting |
| **Custom Forms** | Modified or created forms | Users may see different fields than the standard form |
| **Custom Transactions** | User-created transaction types | May have different posting logic than standard transactions |
| **SuiteScript** | User event, client, scheduled, map/reduce | Can override standard behavior entirely |
| **SuiteFlow (Workflows)** | Automated processes | May add approval steps, field updates, or status changes |
| **SuiteTalk** | SOAP/REST web services | May create or update records outside standard UI |
| **RESTlets** | Custom REST endpoints | May process data differently than UI workflows |
| **Mass Updates** | Automated bulk updates | May modify records in unexpected ways |

## Customization Discovery Questions

| Question | Why It Matters |
|---|---|
| Are there custom scripts on the affected record type? | Scripts can override standard save, submit, update, or delete behavior. |
| Are there workflows on the affected transaction? | Workflows may add approval steps or field changes. |
| Are there custom fields on the affected record? | Custom fields with validation or mandatory settings can block transactions. |
| Was anything customized recently? | Recent changes are the most common cause of new problems. |
| Were any bundles installed or updated recently? | Bundle updates can add new scripts or modify existing ones. |

## How Customizations Affect Standard Processes

| Standard Process | How Customization Can Break It |
|---|---|
| **Purchase Order approval** | A workflow adds an additional approval step that blocks the standard workflow. |
| **Sales Order fulfillment** | A user event script changes the fulfillment quantity or location. |
| **Inventory adjustment** | A custom field is required but not populated. |
| **Period close** | A scheduled script has not completed, preventing close. |
| **Item Receipt creation** | A client script validates data that the user does not have. |

## Script Governance Considerations

Customers with high customization levels may encounter:

- **Script governance limits**: API call limits per script per day
- **Concurrent script limits**: Maximum scripts running simultaneously
- **Execution time limits**: Script timeout thresholds
- **Memory limits**: Data size restrictions in scripts
- **Usage limits**: Overall account-level script execution quotas

When troubleshooting, always ask:
- Are there any script governance errors?
- Has the customer seen "The script has exceeded the maximum execution time" errors?
- Do errors occur at specific times of day (when scheduled scripts run)?

## Suspicious Patterns

| Pattern | Likely Cause |
|---|---|
| Error only on one record but not others | Custom validation on a specific field value |
| Error only at certain times | Scheduled script processing |
| Error on save but not on view | User event script (beforeSubmit) |
| Error related to a specific user | Permission check in a script |
| Error after a bundle update | Bundle script change |
| Error after an import | Data does not meet custom field validation |

## Related Documents

- [NetSuite Configuration](netsuite-configuration.md)
- [Metadata Collection](metadata-collection.md)
- [Escalation Intelligence](escalation-intelligence.md)

## Oracle References

- [Oracle NetSuite Help Center: SuiteScript](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: SuiteFlow](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)