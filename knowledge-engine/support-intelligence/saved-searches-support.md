# Saved Searches Support Intelligence

## Common Customer Questions

| Question | Domain |
|---|---|
| "The saved search is returning wrong results." | Search results |
| "The formula isn't working." | Formula errors |
| "The search is running too slowly." | Performance |
| "I can't see all the results." | Result limits |
| "The summary type isn't calculating correctly." | Summary types |
| "The filter isn't working." | Available filters |
| "Other users can't see my search." | Audience/sharing |

## Questions to Ask First

1. What is the saved search ID or name?
2. What results are you seeing vs. what do you expect?
3. When did the search last work correctly?
4. Were there any recent changes to the search criteria or results?
5. Is this search used in a dashboard, email, or other function?
6. How many results is the search returning?

## Information Required Before Troubleshooting

- Saved search name and ID
- Expected results description
- Actual results or error message
- Search criteria, results, and filter tabs
- Any formulas used
- User who is running the search
- Whether results are limited by audience or role

## Records to Inspect

| Symptom | Inspect This First |
|---|---|
| Wrong results | Criteria tab (are conditions correct?), Results tab (fields selected?), Available Filters tab |
| Formula error | Formula syntax, field IDs, parentheses, data types |
| Too slow | Search type (summary searches are slower), result count, filter efficiency, indexed fields |
| Can't see results | Audience tab, role restriction, search status (public/private) |

## Common Root Causes

| Symptom | Most Likely Causes |
|---|---|
| Wrong results | 1. Criteria condition uses OR instead of AND. 2. Filter is overriding criteria. 3. Summary type is grouping unexpectedly. 4. Date range is incorrect. |
| Formula not working | 1. Field ID is incorrect. 2. Formula uses wrong data type (numeric field in text formula). 3. Missing parentheses. 4. Formula references a field not in results. |
| Search too slow | 1. No index on filtered fields. 2. Too many results. 3. Summary type with many groups. 4. Complex formula in results. |
| Can't share search | 1. Search is set to Private. 2. Audience not configured. 3. Role does not have access to search type. |

## Support Conversation Pattern

**Customer says**: "My saved search is showing 10,000 results but I only expect about 500."

**Interpretation**: The criteria are too broad, or a filter is not being applied as expected.

**Questions to ask**:
- What criteria did you set?
- Are the criteria using AND or OR conditions?
- Are there any Available Filters that might override the criteria?
- Is the search a summary type?

**Evidence required**: Full criteria tab, results tab, available filters tab.

**Most likely causes**:
1. Criteria are connected with OR instead of AND
2. Available Filter is overriding a criteria condition
3. Date range is broader than intended
4. Criteria condition uses "is" instead of "contains" or vice versa

**Verification steps**:
1. Review each criteria line and how they are connected (AND/OR)
2. Check Available Filters for conditions matching criteria
3. Test with a minimal criteria set and add conditions one at a time
4. Check if the search is filtering on a date range as expected

**Recommended solution**:
- Change OR conditions to AND where appropriate
- Remove duplicate conditions between Criteria and Available Filters
- Add additional criteria to narrow results

**Escalate if**: The search returns incorrect results even with minimal criteria, or if the issue involves SuiteScript-based search creation.

## Related Saved Searches

- Search usage statistics
- Search performance log
- Recently modified searches

## Related Workflows

- Saved Search Approval Workflow (if used for formal reporting)
- Email Schedule Workflow

## Related SuiteScript Considerations

- SuiteScript can create, modify, and run saved searches programmatically
- Script-based searches may have different results than UI-based searches
- Custom search filters may be added by SuiteScript

## Related Modules

- [All ERP modules] — saved searches used across the entire system
- [Reporting](../saved-searches/README.md)

## Escalation Criteria

Escalate when:
- Saved search returns different results when run by different users (potential role-based filtering issue)
- Search performance is severely degraded and affecting system performance
- SuiteScript-based search is returning unexpected results
- Search formula references custom fields that may have been changed

## Oracle References

- [Oracle NetSuite Help Center: Saved Searches](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Saved Search Formulas](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)