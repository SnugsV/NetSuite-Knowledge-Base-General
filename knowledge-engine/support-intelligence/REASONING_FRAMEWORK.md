# AI Reasoning Framework

## Purpose

Defines the core reasoning methodology used by every domain support document. This framework teaches an AI how to think through NetSuite support problems.

## The Support Conversation Pattern

Every support interaction follows this structure:

```
Customer says "X isn't working"
         ↓
Interpret what they probably mean
         ↓
Ask clarifying questions
         ↓
Gather evidence / inspect records
         ↓
Identify most likely root causes
         ↓
Verify each cause systematically
         ↓
Recommend solution
         ↓
Escalate if unresolved
```

## Step 1: Interpret the Customer Statement

Customers rarely describe the root cause. They describe symptoms. Map their statement to likely underlying problems.

| Customer Says | They Probably Mean |
|---|---|
| "The work order won't build" | Components are missing or short, BOM issue, status problem |
| "Inventory is wrong" | Quantities don't match physical count, or valuation is incorrect |
| "Revenue is too low this month" | Orders not fulfilled, invoices not created, revenue not recognized |
| "The report is wrong" | Saved search criteria incorrect, data not yet updated, filter issue |
| "We can't close the period" | Unposted transactions, unreconciled accounts, open work orders |

## Step 2: What Information Is Required?

Before diagnosing, gather this minimum context:

- **Module and feature**: Which ERP module? Which specific feature?
- **Time frame**: When did it work last? When did it stop working?
- **Scope**: Affects one record, one user, or all users?
- **Error messages**: Exact text of any errors
- **Recent changes**: Any system updates, configuration changes, or data imports
- **Transaction IDs**: Specific record numbers if known

## Step 3: What to Inspect First

In most cases, inspect these records in order:

1. **The affected record**: Status, dates, quantities, user assignments
2. **Related records**: Parent documents, child transactions
3. **Activity log / audit trail**: Who did what and when
4. **Configuration**: Feature settings, preferences, permissions
5. **Saved Searches**: Summary-level views for pattern detection

## Step 4: Cause Elimination

Test each likely cause in order of probability:

| Priority | Approach |
|---|---|
| 1 | Check the simplest cause first (status, permissions, data entry) |
| 2 | Check transaction sequencing (was a required step skipped?) |
| 3 | Check configuration (feature enabled? setting correct?) |
| 4 | Check integration (are connected systems in sync?) |
| 5 | Check data integrity (corruption, orphaned records, mismatches) |

## Step 5: Verification

Before recommending a solution, verify the diagnosis:

- Can you reproduce the issue in a sandbox?
- Does the proposed fix address all symptoms?
- Are there secondary effects of the proposed fix?
- Does the customer agree with the diagnosis?

## Step 6: Solution Recommendation

Structure recommendations as:

- **Root cause**: What was wrong
- **Fix**: What to do
- **Evidence**: How to confirm it worked
- **Prevention**: How to avoid recurrence

## Step 7: Escalation Criteria

Escalate to a human expert when:

| Criterion | Example |
|---|---|
| **Data integrity issue** | Corrupted records, orphaned transactions |
| **Feature limitation** | NetSuite limitation requiring SuiteScript or customization |
| **Account-level problem** | Performance issue, account configuration error |
| **Security or compliance** | Audit concern, access control conflict |
| **Root cause not found** | After exhausting all likely causes |
| **Customer insists on wrong solution** | Customer demands a change that will cause other problems |

## Related Documents

- All domain support documents in this directory