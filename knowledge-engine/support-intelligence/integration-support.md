# Integration Support Intelligence

## Common Customer Questions

| Question | Domain |
|---|---|
| "Data from our e-commerce platform isn't syncing." | E-commerce integration |
| "The bank feed isn't updating." | Bank integration |
| "EDI orders aren't coming through." | EDI |
| "The CSV import failed." | Data import |
| "Our shipping system isn't getting orders." | Shipping integration |
| "Data from the vendor portal isn't matching." | Vendor portal |
| "The SuiteApp stopped working." | SuiteApp integration |

## Questions to Ask First

1. Which integration is affected?
2. When did the integration last work successfully?
3. Have there been any changes to the external system?
4. Are there any error logs or error messages?
5. Is this affecting all data or only specific records?
6. Was there a recent NetSuite release or update?

## Information Required Before Troubleshooting

- Integration name or type (e.g., "Shopify connector")
- Error message or log entry
- Last successful sync date/time
- Records affected (order IDs, customer IDs, SKUs)
- External system version and any recent updates
- NetSuite account ID

## Records to Inspect

| Symptom | Inspect This First |
|---|---|
| E-commerce not syncing | Integration status, error log, mapping configuration, OAuth token expiry |
| Bank feed not updating | Bank feed status, last refresh date, bank record, connection status |
| CSV import failed | Import log, CSV file format, field mapping, required fields |
| EDI not processing | EDI status log, partner configuration, map validation, test file results |

## Common Root Causes

| Symptom | Most Likely Causes |
|---|---|
| E-commerce integration stopped | 1. API token expired. 2. External system changed API. 3. Rate limit exceeded. 4. Network issue. |
| CSV import fails | 1. File format incorrect. 2. Required fields missing. 3. Data validation errors. 4. Duplicate records. |
| Bank feed not updating | 1. Bank credentials changed. 2. Bank requires re-authentication. 3. Feed provider issue. |
| EDI not processing | 1. Partner certificate expired. 2. EDI map version mismatch. 3. Trading partner configuration changed. |

## Support Conversation Pattern

**Customer says**: "Orders from our website stopped syncing to NetSuite yesterday."

**Interpretation**: An integration between the e-commerce platform and NetSuite has failed. The most common causes are authentication expiry, API changes, or configuration drift.

**Questions to ask**:
- Which e-commerce platform are you using?
- What is the integration method (native connector, SuiteApp, custom)?
- When was the last successful sync?
- Are there any error messages in the integration log?
- Were there any updates to the e-commerce platform recently?

**Evidence required**: Integration name, error logs, last sync timestamp, external system update history.

**Most likely causes**:
1. API token or OAuth credentials expired
2. The e-commerce platform updated its API
3. Rate limiting from the external system
4. Network connectivity issue
5. SuiteApp needs to be updated

**Verification steps**:
1. Check the integration's error log for specific errors
2. Verify API credentials are still valid
3. Check if the external system is accessible
4. Test with a single record if possible
5. Check for NetSuite or SuiteApp updates

**Recommended solution**:
- Re-authenticate the integration (refresh OAuth token)
- Update the SuiteApp to the latest version
- Contact the e-commerce platform's support for API status
- If custom integration, review the integration script for errors

**Escalate if**: The integration is custom-built and the error is in the script code, or if the issue requires changes to the external system's API.

## Related Saved Searches

- Integration error log
- Recently imported records
- Failed imports by type
- SuiteApp version history

## Related Workflows

- Integration Health Check Workflow
- Automated Import Workflow
- Error Notification Workflow

## Related SuiteScript Considerations

- Custom integrations use SuiteScript (RESTlets, SuiteTalk, OAuth)
- Integration scripts may have API call limits
- Custom scripts may need updates after NetSuite releases
- Error handling in custom scripts determines integration reliability

## Related Modules

- [All ERP modules] — integrations affect every module
- [Administration](../administration/README.md) — integration setup

## Escalation Criteria

Escalate when:
- Integration failure is caused by a NetSuite update or change
- Custom SuiteScript integration has code errors
- Data integrity issue has occurred (duplicate or missing records)
- Integration has been down for more than 24 hours
- Security concern (unauthorized data access, credential compromise)

## Oracle References

- [Oracle NetSuite Help Center: Integrations](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: SuiteTalk Web Services](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: REST Web Services](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)