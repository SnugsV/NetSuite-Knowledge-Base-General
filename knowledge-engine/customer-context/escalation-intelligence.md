# Escalation Intelligence

## Purpose

Escalation intelligence determines when the AI should continue troubleshooting independently, when it should request more metadata, when a customer-side administrator is needed, when a developer should be involved, and when Oracle Support is appropriate.

## Escalation Levels

| Level | Who Acts | When |
|---|---|---|
| **The AI continues** | AI | Root cause is clear, fix is known, environment matches expectations |
| **Request more metadata** | Customer | Insufficient information to diagnose — needs specific records, screenshots, or logs |
| **Involve NetSuite admin** | Customer admin | Configuration changes, permission adjustments, or feature enablement needed |
| **Involve developer** | Customer developer | SuiteScript, SuiteFlow, or customization issue |
| **Escalate to senior** | Senior support | Root cause not found, cross-module issue, complex data integrity problem |
| **Oracle Support** | Oracle | Account-level issue, performance problem, suspected bug, release-related issue |

## Escalation Decision Tree

```
Is the root cause clearly identified and fixable by the customer?
  ├── Yes → The AI continues. Provide recommendation.
  │
  └── No → Is more metadata needed?
            ├── Yes → Request specific records, screenshots, or error logs.
            │
            └── No → Is the fix a configuration change that requires an admin?
                        ├── Yes → Involve NetSuite admin.
                        │
                        └── No → Is the fix a customization change?
                                    ├── Yes → Involve developer.
                                    │
                                    └── No → Is the issue beyond AI scope?
                                                ├── Yes → Escalate to senior support or Oracle.
                                                │
                                                └── No → Return to root cause analysis.
```

## When to Request More Metadata

| Situation | Metadata Needed |
|---|---|
| Root cause uncertain | Transaction record, error log, configuration screenshots |
| Configuration unclear | Feature enablement screenshots, role permissions |
| Customization suspected | Script deployments, workflow definitions, custom fields |
| Performance issue | Time of occurrence, affected records, error logs |
| Integration failure | Integration logs, API responses, error codes |

## When to Involve a NetSuite Administrator

| Situation | Why |
|---|---|
| Feature needs to be enabled | Admin access required for feature enablement |
| Role or permission change needed | Admin access required for role configuration |
| Account-level configuration | Admin access required for company preferences |
| Period close action | Admin access required for period actions |

## When to Involve a Developer

| Situation | Why |
|---|---|
| Script error | Developer access required to view and modify scripts |
| Customization issue | Developer access required for SuiteScript or SuiteFlow |
| Integration failure | Developer access required for RESTlets or SuiteTalk |
| Custom record or field modification | Developer or admin access for record configuration |

## When to Escalate to Senior Support or Oracle

| Situation | Reason |
|---|---|
| Root cause not found | After exhaustive investigation, the cause is unknown |
| Suspected system bug | The behavior appears to be a system issue, not a configuration problem |
| Account-level performance issue | Affecting all users, all modules — may be an account-level problem |
| Release-related behavior change | Started after a NetSuite release update |
| Data integrity concern | Suspected corruption that may require Oracle intervention |
| Security or compliance issue | Unauthorized access, data exposure, audit trail gaps |

## What to Include in an Escalation

When escalating, include:

- **Summary**: One-sentence description of the issue
- **Customer context**: Industry, configuration, customizations
- **What was tried**: Steps already taken and results
- **Metadata gathered**: Records inspected, logs reviewed, screenshots collected
- **Hypothesis**: What the AI believes is happening
- **Remaining unknowns**: What is still uncertain
- **Recommendation**: What the AI suggests the next person should do

## Escalation Example

```
Summary: Customer cannot close the July 2026 period due to an unposted transaction
that does not appear in the standard unposted transaction report.

Customer context: Wholesale distributor, OneWorld, 3 subsidiaries, 50 users.
Standard configuration with ~15 custom fields on the sales order record.

What was tried:
1. Ran the standard unposted transaction report — no results
2. Checked each subsidiary individually — no results
3. Ran a saved search for transactions with status = Pending Approval — found 1 sales order
4. Approved and posted the sales order — period close still blocked
5. Checked period close readiness report — says "unposted transaction exists"

Metadata gathered: Period close readiness report, transaction search results,
audit trail for the period.

Hypothesis: A custom script or workflow is creating a ghost transaction that
the standard reports cannot find but the period close validation detects.

Remaining unknowns: Whether any custom scripts create journal entries or
transactions during the close process.

Recommendation: A developer should review any scripts or workflows that
run during the period close to identify any that create transactions.
```

## Related Documents

- [Solution Confidence](solution-confidence.md)
- [Problem Classification](problem-classification.md)
- [Metadata Collection](metadata-collection.md)
- [Customizations](customizations.md)

## Oracle References

- [Oracle NetSuite Help Center: Support](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: My Oracle Support](https://support.oracle.com/)