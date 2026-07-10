# Screenshot and Log Redaction Checklist

## Quick Summary

Screenshots, logs, EDI messages, API errors, tax responses, labels, and connector traces can be useful for support, but they often contain private data. Redact first, then document the generic troubleshooting pattern.

## Public-Safe Boundary

Never publish raw production screenshots, raw logs, raw EDI documents, tax responses, labels, carrier responses, connector traces, API payloads, credentials, customer records, orders, invoices, or support tickets in this repository.

## Redact These Values

### Customer and Partner Data

Remove or replace:

- Customer names
- Vendor names
- Trading partner names when tied to private requirements
- Contact names
- Email addresses
- Phone numbers
- Ship-to and bill-to addresses
- Store/DC identifiers
- Account numbers

### Transaction Data

Remove or replace:

- Sales order numbers
- Purchase order numbers
- Item Fulfillment numbers
- Invoice numbers
- Credit memo numbers
- Return authorization numbers
- Payment numbers
- Tracking numbers
- Label IDs
- EDI control numbers
- Document IDs

### Financial and Tax Data

Remove or replace:

- Prices
- Discounts
- Freight charges
- Tax amounts
- Exemption certificate details
- Filing/return totals
- Chargeback amounts
- Negotiated carrier rates
- Payment terms when private

### Technical Secrets

Remove or replace:

- API keys
- Tokens
- Passwords
- Consumer keys
- Account IDs when sensitive
- VAN/mailbox credentials
- OAuth signatures
- Internal URLs
- Script deployment IDs tied to private implementation
- Raw request/response payloads

### Implementation Details

Remove or replace:

- Custom field IDs
- Custom script names
- Workflow names
- Saved search names
- EDI map names
- Carrier account setup
- Tax policy rules
- Warehouse SOPs
- Private approval rules
- Internal role names

## Safe Replacement Style

Use neutral placeholders:

- `Customer A`
- `Item A`
- `Sales Order 12345`
- `Invoice 12345`
- `Tracking Number X`
- `Carrier A`
- `Trading Partner A`
- `Location A`
- `Tax Amount X`
- `Custom Field A`
- `Connector Error X`

Do not preserve real value shape if the value itself could identify the organization, customer, partner, or transaction.

## Screenshot Review Checklist

Before using a screenshot:

1. Crop to the smallest useful area.
2. Remove names, numbers, addresses, totals, and identifiers.
3. Remove browser tabs, bookmarks, URLs, account names, and environment labels if sensitive.
4. Remove custom field IDs, script names, workflow names, and saved search names.
5. Replace exact amounts or quantities with generic values unless they are essential and fictional.
6. Confirm the screenshot teaches a generic pattern, not a private operating procedure.

## Log Review Checklist

Before using a log excerpt:

1. Use the shortest useful excerpt.
2. Remove timestamps if they reveal internal activity patterns.
3. Remove account IDs, tokens, URLs, and payloads.
4. Remove customer, item, transaction, and partner identifiers.
5. Summarize long stack traces instead of copying them.
6. Keep only the generic error category and safe message pattern.

## EDI and API Payload Checklist

Before using EDI or API content:

1. Do not publish raw payloads.
2. Summarize the document type and failing data category.
3. Replace partner, item, quantity, price, and document identifiers.
4. Avoid exposing segment-level partner requirements unless they are public and generic.
5. Keep map details and credentials private.

## AI Assistant Response Pattern

When a user provides a screenshot or log, the assistant should:

1. Treat it as private by default.
2. Extract only safe troubleshooting clues.
3. Ask for redacted context rather than raw records when possible.
4. Avoid repeating sensitive values back to the user unless necessary within the private support context.
5. If turning the issue into documentation, generalize the pattern and remove implementation details.

## Related Articles

- [Cross-Vendor Support](README.md)
- [Cross-Vendor Incident Intake Checklist](integration-incident-intake-checklist.md)
- [NetSuite Error Diagnostic Framework](../advanced-troubleshooting/netsuite-error-diagnostic-framework.md)
- [Screenshot and Error Message Triage](../advanced-troubleshooting/screenshot-and-error-message-triage.md)
