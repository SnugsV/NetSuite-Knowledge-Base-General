---
title: Integration Error Triage
module: Advanced Troubleshooting
difficulty: Advanced
estimated_time: 25 minutes
status: Draft
last_reviewed:
---

# Integration Error Triage

## Quick Summary

NetSuite integration errors usually involve authentication, role permissions, endpoint configuration, payload structure, record validation, transaction state, script/workflow behavior, middleware mapping, or vendor connector behavior. Good triage separates transport errors from NetSuite record errors and business-rule errors.

## Difficulty

Advanced

## Estimated Time

25 minutes

## Prerequisites

You should understand:

- NetSuite records and transactions
- Roles and permissions
- SuiteTalk REST or SOAP concepts
- RESTlets or Suitelets if used
- CSV import basics
- Middleware or connector logs when applicable

## Overview

An integration failure is rarely just an API problem. NetSuite may reject a request because the integration role lacks permission, the payload is missing required data, a workflow or script blocks save, a transaction is in the wrong status, a posting period is closed, or an external connector maps data incorrectly.

The first goal is to identify where the failure happened:

- Before reaching NetSuite
- During authentication
- During request routing
- During NetSuite record validation
- During workflow or script execution
- During downstream connector processing
- During response handling in the external system

## Integration Types

Common NetSuite integration paths include:

- SuiteTalk REST Web Services
- SuiteTalk SOAP Web Services
- RESTlets
- Suitelets
- CSV imports
- SFTP or file-based middleware
- iPaaS platforms
- Vendor connectors such as Pacejet, SPS Commerce, Avalara, ecommerce, WMS, or EDI tools
- Scheduled scripts or Map/Reduce scripts that exchange data externally

## First Questions to Ask

1. Which integration path is involved?
2. What operation failed: create, update, delete, transform, search, authenticate, import, export, or callback?
3. What system initiated the request?
4. What timestamp did the failure occur?
5. What record type was being created or updated?
6. What response status, error code, or message was returned?
7. Does the same action work manually in the NetSuite UI?
8. Did anything change recently: credentials, role, endpoint, mapping, script, workflow, vendor release, bundle, or NetSuite release?

## Error Categories

### Authentication Error

Likely causes:

- Expired or incorrect credentials
- Token, certificate, OAuth, or integration record issue
- Wrong account or environment
- Wrong domain or endpoint
- Disabled integration user or role

Evidence to collect:

- Authentication method
- Endpoint domain
- Environment: production, sandbox, release preview
- Timestamp
- External system auth log
- NetSuite integration or login audit context if available

### Authorization or Permission Error

Likely causes:

- Integration role lacks record permission
- Role can create but not edit, delete, approve, fulfill, bill, or transform
- Subsidiary, department, class, location, employee, or data restriction blocks access
- Search, script, or custom record permission is missing

Evidence to collect:

- Integration role
- Record type
- Operation attempted
- Permission level required
- Whether the same role can perform the action in UI

### Payload or Schema Error

Likely causes:

- Missing required field
- Invalid field value
- Wrong data type
- Invalid internal ID or external ID
- Unsupported sublist or subrecord structure
- Invalid date, currency, subsidiary, location, item, customer, or tax value

Evidence to collect:

- Sanitized request payload
- Record type and operation
- Required fields
- REST API Browser or schema reference
- Working example payload if available

### NetSuite Record Validation Error

Likely causes:

- Required body or line field is missing
- Transaction status does not allow the operation
- Posting period is closed
- Inventory detail is incomplete
- Bin, lot, serial, or inventory status detail is required
- Customer, item, subsidiary, location, currency, or tax setup blocks the transaction

Evidence to collect:

- Exact NetSuite error
- Record status
- Related record IDs or external IDs in sanitized form
- Transaction date and period
- Item, location, subsidiary, and inventory context

### Script or Workflow Error

Likely causes:

- User event script blocks save
- Workflow returns a user error
- Script assumes UI context but receives API context
- Script does not handle missing values from integration payload
- Governance, timeout, or search issue occurs during automated processing

Evidence to collect:

- Script execution logs
- Workflow history
- Deployment context
- Timestamp
- User or integration role
- Payload fields involved

### Middleware or Connector Mapping Error

Likely causes:

- Source field mapped to wrong NetSuite field
- Required value not transformed correctly
- External ID mismatch
- Record lookup fails
- Connector caches stale metadata
- Vendor platform changed behavior

Evidence to collect:

- Mapping name or flow name
- Source record sample with private data removed
- Destination record type
- Lookup keys
- Middleware logs
- Vendor connector logs

## REST and SOAP Triage Pattern

For SuiteTalk REST or SOAP issues:

1. Confirm the endpoint and environment.
2. Confirm authentication succeeded.
3. Confirm the integration role has least-privilege access for the operation.
4. Confirm the record type and operation are supported.
5. Validate required fields and sublists.
6. Compare payload to a working UI-created record.
7. Check whether scripts or workflows run in web services context.
8. Review response body, not only HTTP status.

## RESTlet and Suitelet Triage Pattern

For RESTlet or Suitelet issues:

1. Confirm the script deployment is active.
2. Confirm the role can execute the script.
3. Confirm request method and parameters.
4. Check script logs at the failure timestamp.
5. Determine whether the script failed before or after touching NetSuite records.
6. Review downstream record validation errors.
7. Confirm the script does not expose or log private data unnecessarily.

## CSV Import Triage Pattern

CSV import issues often look like integration errors because they create or update records in bulk.

Check:

- Import type and record type
- Field mapping
- Required fields
- External IDs and references
- Date, currency, subsidiary, location, and item values
- Whether scripts and workflows run during import
- Import status results and error file

## Vendor Connector Triage Pattern

For Pacejet, SPS Commerce, Avalara, or other connectors:

1. Identify whether NetSuite or the vendor system originated the action.
2. Capture the connector error message and timestamp.
3. Check whether NetSuite accepted, rejected, or never received the transaction.
4. Review related NetSuite records and connector logs.
5. Confirm whether the issue began after a vendor release, mapping update, credential change, bundle update, or NetSuite release.
6. Escalate to the connector owner when behavior depends on private setup or vendor support.

## AI Assistant Response Pattern

When a user asks about an integration error, the assistant should:

1. Identify the integration path.
2. Separate authentication, permission, payload, record validation, script/workflow, and connector possibilities.
3. Ask for exact error text, timestamp, operation, record type, and sanitized payload or log excerpt.
4. Suggest low-risk checks first.
5. Avoid requesting secrets or credentials.
6. Avoid publishing private payloads, mappings, screenshots, or customer data.
7. Recommend escalation when the issue depends on private configuration, code, credentials, or vendor support.

## Best Practices

- Use least-privilege integration roles.
- Keep endpoint and environment configurable.
- Log request IDs, timestamps, and sanitized context.
- Avoid logging credentials or sensitive payloads.
- Test create, update, transform, and search operations separately.
- Compare integration-created records to UI-created records.
- Document supported record types and known limitations.
- Monitor vendor release notes for connector changes.

## Common Mistakes

- Treating all integration errors as authentication problems.
- Ignoring NetSuite role permissions.
- Sending UI-only assumptions through API payloads.
- Not checking user event scripts or workflows.
- Not reviewing the full response body.
- Hardcoding account IDs, internal IDs, or environment URLs.
- Sharing private payloads in public troubleshooting documentation.

## Escalation Criteria

Escalate when:

- Credentials, tokens, certificates, or OAuth setup must be changed.
- The issue involves proprietary mappings or private connector setup.
- A SuiteScript or workflow must be modified.
- The transaction affects financial posting, inventory, tax, or fulfillment.
- The vendor connector returns an undocumented or platform-level error.
- The failure is intermittent and requires log correlation across systems.

## Related Articles

- [NetSuite Error Diagnostic Framework](netsuite-error-diagnostic-framework.md)
- [SuiteScript and Workflow Error Triage](suitescript-and-workflow-error-triage.md)
- [SuiteTalk REST Web Services Overview](../suitetalk/rest-overview.md)
- [SuiteScript Overview](../suitescript/overview.md)
- [Pacejet Shipping Integration](../integrations/pacejet/README.md)

## Oracle References

- Oracle NetSuite Help Center: SuiteTalk REST Web Services documentation
- Oracle NetSuite Help Center: SuiteTalk SOAP Web Services documentation
- Oracle NetSuite Help Center: RESTlets documentation
- Oracle NetSuite Help Center: CSV import documentation
- Oracle NetSuite Help Center: Roles and permissions documentation
