# Avalara Connector Sync Failure and Log Review

## Purpose

Provide a structured way to troubleshoot Avalara connector, sync, API, and log issues related to NetSuite transactions.

## Source Status

Based on public Avalara Developer documentation, the Avalara Knowledge Center, Avalara NetSuite integration information, and existing repository Avalara data-flow articles. Exact log names, connector settings, and retry behavior depend on the installed connector and account configuration.

## Quick Summary

Connector issues should be diagnosed in layers: trigger, data sent, authentication, authorization, validation, Avalara response, NetSuite writeback, retry behavior, and user-facing transaction result.

## First Questions to Ask

1. Is the issue tax calculation, address validation, exemption sync, transaction sync, or connector setup?
2. Is the error visible in NetSuite, Avalara, middleware, or an API response?
3. Did the transaction data reach Avalara?
4. Did Avalara return a result or an error?
5. Did NetSuite store the returned result?
6. Does the issue affect one transaction, one customer, one item, one subsidiary/location, or all transactions?
7. Did credentials, connector settings, role permissions, fields, scripts, workflows, or release versions change recently?

## Diagnostic Layers

### Layer 1: Trigger

Check:

- Transaction type
- Save/edit/approve/invoice timing
- Connector trigger settings
- Import vs UI vs integration context
- Whether workflow or script timing changed transaction data before calculation

### Layer 2: Request Data

Check:

- Customer identifier
- Address data
- Item lines
- Amounts
- Shipping, discounts, fees
- Date
- Exemption indicators
- Location or origin data

### Layer 3: Authentication and Authorization

Check:

- Connector credentials
- Token or API access status
- Environment mismatch
- NetSuite role permissions
- Avalara account access
- Credential rotation or revocation

### Layer 4: Validation and Response

Check:

- Required fields
- Address validation errors
- Invalid customer, item, or tax code mapping
- Avalara response code or message
- Middleware-translated error
- Partial success behavior

### Layer 5: NetSuite Writeback

Check:

- Tax fields updated
- Transaction totals updated
- Error stored or displayed
- User permissions to view tax fields
- Workflow/script changes after connector response
- Transaction status preventing update

### Layer 6: Retry and Duplicate Prevention

Check:

- Whether retry is safe
- External ID or transaction identifier
- Duplicate transaction risk
- Partial posting or partial sync
- Whether a failed attempt already created an Avalara-side record

## Common Symptoms

### Connector Error but No User-Friendly Message

Likely causes:

- Raw API error surfaced in NetSuite
- Middleware transformed message poorly
- Logging level insufficient
- Error occurred after transaction save
- User lacks access to detailed logs

### Tax Calculates in Avalara but Not NetSuite

Likely causes:

- Writeback failed
- Transaction status prevents update
- User role cannot see result field
- Workflow or script overwrote tax fields
- Connector error after successful calculation

### NetSuite Sent Wrong Data

Likely causes:

- Field mapping issue
- Transaction-level address override
- Item mapping mismatch
- Import or integration omitted fields
- Workflow/script changed data before connector trigger

### Retrying Creates Risk

Likely causes:

- Original request partially succeeded
- Transaction was committed in Avalara but not updated in NetSuite
- External ID or document code mismatch
- Connector does not handle idempotency as expected

## Safe Diagnostic Path

1. Capture sanitized error text and timestamp.
2. Identify transaction type, trigger point, and environment.
3. Confirm whether data reached Avalara.
4. Confirm response or error returned by Avalara.
5. Confirm whether NetSuite wrote back the result.
6. Check role permissions, transaction status, workflows, and scripts.
7. Determine whether retry is safe before retrying.
8. Escalate credential, connector configuration, or production sync issues through the proper support path.

## AI Assistant Response Pattern

When a user asks about an Avalara connector or sync issue, the assistant should:

1. Ask where the error appears: NetSuite, Avalara, middleware, or API response.
2. Ask whether data reached Avalara and whether a response returned.
3. Diagnose trigger, request data, auth, validation, response, writeback, and retry layers.
4. Warn against blind retries when the original request may have partially succeeded.
5. Avoid requesting credentials, tokens, raw production logs, or private connector settings.

## Related Articles

- [NetSuite Transaction Tax Flow](NETSUITE_TRANSACTION_TAX_FLOW.md)
- [Tax Calculation Troubleshooting](TAX_CALCULATION_TROUBLESHOOTING.md)
- [Avalara Data Flow](DATA_FLOW.md)
- [Record Relationships](RECORD_RELATIONSHIPS.md)
- [Source Guide](SOURCE_GUIDE.md)

## Public References

- Avalara Knowledge Center: https://knowledge.avalara.com/
- Avalara Developer documentation
- Avalara NetSuite integration page
