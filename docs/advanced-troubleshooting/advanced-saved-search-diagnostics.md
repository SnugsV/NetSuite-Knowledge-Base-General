---
title: Advanced Saved Search Diagnostics
module: Advanced Troubleshooting
difficulty: Advanced
estimated_time: 30 minutes
status: Draft
last_reviewed:
---

# Advanced Saved Search Diagnostics

## Quick Summary

Saved search problems usually come from one of five layers: record type, criteria, joins, formulas, or audience/permissions. Diagnose the layer before changing the search.

## Difficulty

Advanced

## Estimated Time

30 minutes

## Prerequisites

You should understand:

- Basic saved search creation
- Criteria and results
- Summary searches
- Formulas
- Joins
- Roles and permissions
- Transaction status and main line behavior

## Overview

Saved searches often become business-critical reporting logic. When a saved search returns the wrong rows, hides expected data, duplicates results, times out, or behaves differently by role, the issue is rarely solved by changing one filter at random.

A good diagnostic process separates the problem into layers:

- Is the search built on the correct record type?
- Are criteria excluding expected records?
- Are joins multiplying or hiding rows?
- Are formulas evaluating differently than expected?
- Are summary settings changing the result grain?
- Is the user allowed to see the records or fields?
- Did a release, bundle, workflow, field change, or role change affect the result?

## Public-Safe Boundary

Keep examples generic. Do not publish company-specific saved search names, custom field IDs, formulas, screenshots, customer names, pricing, financial results, or private reporting logic.

## First Questions to Ask

When diagnosing a saved search, ask:

1. What record type is the search based on?
2. What result is wrong: missing rows, extra rows, duplicate rows, wrong totals, formula errors, or role-specific visibility?
3. Did the issue start after a change to roles, fields, forms, workflows, bundles, scripts, accounting periods, or NetSuite release behavior?
4. Does the problem happen for all users or only certain roles?
5. Does the issue happen in both edit mode and dashboard/report output?
6. Is the search detail-level, summary-level, or both?
7. Are transaction lines involved?
8. Are joins used in criteria, results, or formulas?
9. Are custom fields, sourced fields, or formula fields involved?
10. Is the search used by a workflow, script, KPI, dashboard, report, integration, or export?

## Diagnostic Layers

### Layer 1: Record Type

Symptoms:

- Expected fields are unavailable
- Expected records never appear
- Joins feel awkward or indirect
- Transaction line behavior is confusing

Checks:

- Confirm the base record type matches the business question.
- For transaction searches, confirm whether the question is header-level or line-level.
- Check whether a specialized record type would be clearer than a broad transaction search.
- Confirm whether the search should use a standard record, custom record, item, customer, vendor, employee, or transaction record.

### Layer 2: Criteria

Symptoms:

- Expected records are missing
- Results change unexpectedly when one filter is added
- A date, status, subsidiary, location, class, department, or inactive filter removes valid records

Checks:

- Temporarily simplify criteria to the smallest possible version.
- Add criteria back one at a time.
- Check whether criteria use `Any Of`, `None Of`, `Is`, `Is Not`, empty values, or inactive records correctly.
- For transaction searches, review main line, tax line, shipping line, COGS line, posting, and status filters.
- Confirm date filters use the expected date field.

### Layer 3: Joins

Symptoms:

- Duplicate rows appear
- Expected rows disappear when a joined field is added
- Formula fields behave differently from normal result fields
- Filters on joined records narrow the result more than expected

Checks:

- Identify every joined field in criteria, results, sorting, and formulas.
- Confirm whether the join is one-to-one, one-to-many, or optional.
- If rows duplicate, test whether a joined child record is creating multiple result rows.
- If rows disappear, check whether a joined filter requires a related record to exist.
- Consider whether summary grouping is hiding join duplication rather than fixing it.

### Layer 4: Summary and Aggregation

Symptoms:

- Totals are wrong
- Count, sum, min, max, or group results do not match detail results
- A formula works in detail mode but fails in summary mode

Checks:

- Confirm the result grain: one row per record, line, customer, item, period, or group.
- Review every summary type.
- Make sure all displayed fields are intentionally grouped or summarized.
- Compare a detail version of the search to the summary version.
- Check whether duplicate line-level rows are inflating totals.

### Layer 5: Formulas

Symptoms:

- Formula errors appear
- Results are blank unexpectedly
- Numbers or dates sort incorrectly
- Formula output differs by role or context

Checks:

- Confirm the formula type: text, numeric, date, percent, or currency.
- Test the formula in smaller pieces.
- Check null handling.
- Avoid mixing text and numeric comparisons without intentional conversion.
- Confirm whether the formula references joined fields.
- Validate that summary formulas use the correct summary context.

### Layer 6: Audience, Role, and Permission Effects

Symptoms:

- Search works for an administrator but not another role
- A user can open the search but sees missing values
- Dashboard portlet shows fewer results than edit preview
- Export behavior differs by user

Checks:

- Confirm the search audience.
- Confirm whether the user can access the base record type.
- Confirm whether the user can access joined record types.
- Confirm field-level or form-level restrictions where relevant.
- Compare results using a controlled test role.
- Check subsidiary, location, department, class, employee, or custom segment restrictions.

## Common Saved Search Problems

### Missing Transactions

Likely causes:

- Wrong base record type
- Main line or line-level filters
- Status filters
- Date field mismatch
- Posting or non-posting filter
- Subsidiary or accounting-period restrictions
- Role visibility

### Duplicate Rows

Likely causes:

- Line-level transaction results
- Joined one-to-many records
- Multiple applying or applied transactions
- Multiple locations, bins, addresses, contacts, or related records
- Summary grouping that does not match the desired result grain

### Wrong Totals

Likely causes:

- Detail rows being summed more than once
- Summary type mismatch
- Currency or exchange-rate assumptions
- Tax, shipping, discount, or COGS lines included unexpectedly
- Formula using text rather than numeric output

### Formula Error

Likely causes:

- Invalid field reference
- Wrong formula type
- Missing null handling
- Joined field not available in context
- Summary formula used in detail context or detail formula used in summary context

### Role-Specific Results

Likely causes:

- Search audience
- Base record permission
- Joined record permission
- Subsidiary, location, department, class, or custom segment restriction
- Employee restrictions
- Field visibility or custom form differences

## Safe Diagnostic Path

1. Copy the search before experimenting.
2. Record the exact symptom and expected result.
3. Confirm the base record type.
4. Remove or simplify criteria until expected records appear.
5. Reapply criteria one at a time.
6. Add result columns back in groups.
7. Test joins separately.
8. Compare detail and summary versions.
9. Test with the affected role.
10. Document the final business rule in plain language.

## AI Assistant Response Pattern

When a user asks why a saved search is wrong, the assistant should:

1. Ask whether the issue is missing rows, extra rows, duplicate rows, wrong totals, formula errors, or role-specific results.
2. Ask for the base record type and whether transactions are line-level or header-level.
3. Ask whether the search uses joins, summary results, or formulas.
4. Recommend copying the search before testing changes.
5. Diagnose one layer at a time: record type, criteria, joins, summary, formulas, permissions.
6. Avoid inventing exact field IDs or formulas without enough context.
7. Keep examples generic and public-safe.

## Related Articles

- [NetSuite Error Diagnostic Framework](netsuite-error-diagnostic-framework.md)
- [Screenshot and Error Message Triage](screenshot-and-error-message-triage.md)
- [Permissions and Role Difference Diagnostics](permissions-and-role-difference-diagnostics.md)
- [Saved Search Troubleshooting](../saved-searches/troubleshooting.md)
- [Formulas](../saved-searches/formulas.md)

## Oracle References

- Oracle NetSuite Help Center: Search Guide
- Oracle NetSuite Help Center: SuiteAnalytics Workbook Guide
- Oracle NetSuite Help Center: Managing Users and Roles
- Oracle NetSuite Help Center: System Notes Guide
