# Metadata Reasoning

## Purpose

Defines the core methodology for metadata collection — what to collect, why it matters, and how missing metadata affects solution confidence.

## The Metadata Collection Process

### Phase 1: Determine What Metadata Is Required

Based on the solution type (Saved Search, SuiteScript, Workflow, etc.), identify the required metadata.

### Phase 2: Assess What Is Already Known

Check the Customer Context Framework for information already collected about the customer's environment.

### Phase 3: Request Metadata from the Customer

For each missing metadata item, request it from the customer with a clear explanation of why it is needed.

### Phase 4: Validate the Metadata

Confirm the metadata is complete, accurate, and from the correct environment.

### Phase 5: Assess Confidence

Assign a confidence level based on what metadata was collected vs. what was missing.

## Metadata Classification

| Classification | Definition | Impact If Missing |
|---|---|---|
| **Required** | Solution cannot be designed without this | Solution is blocked until collected |
| **Optional** | Solution benefits from this but can proceed without it | Recommendation may need manual review |
| **Nice-to-Have** | Improves solution quality but not essential | Recommendation will be generic |

## Confidence Impact

| Scenario | Confidence | Action |
|---|---|---|
| All required metadata collected | High | Proceed with solution design |
| Required metadata partially collected | Medium | Note gaps, recommend manual review |
| Required metadata mostly missing | Low | Gather more information before proceeding |
| Required metadata completely missing | Unknown | Do not proceed — request metadata first |

## Common Metadata Sources

| Source | What It Provides |
|---|---|
| **Feature enablement screenshots** | Which features are active |
| **Record browser export** | Available fields and IDs per record type |
| **Saved search CSV export** | Actual data from the customer's environment |
| **Role/permission screenshots** | What the target user can see and do |
| **Script deployment list** | What customizations exist |
| **Custom field definition export** | Custom fields, their IDs, types, and validation |
| **Workflow list** | Automated processes currently active |
| **Integration logs** | Current integration activity and error history |
| **Form screenshots** | How records appear to the user |
| **Sample transactions** | Real data that can be used for testing |

## When Enough Metadata Has Been Collected

The following should be true before proceeding:

- [ ] All required metadata is collected for the solution type
- [ ] Optional metadata is collected where available
- [ ] The metadata is from the correct environment (production vs. sandbox)
- [ ] The metadata is recent (within the last 30 days, or since the last significant change)
- [ ] The metadata has been validated (no obvious contradictions or gaps)
- [ ] Confidence is at least Medium

## Related Documents

- [Saved Search Metadata](saved-search-metadata.md)
- [Scripting Metadata](scripting-metadata.md)
- [Configuration Metadata](configuration-metadata.md)
- [Solution Confidence](../customer-context/solution-confidence.md)