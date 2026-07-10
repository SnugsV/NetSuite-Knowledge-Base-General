# Cross-Vendor Release and Update Review Workflow

## Quick Summary

NetSuite, Avalara, Pacejet, and SPS Commerce can all change behavior through product releases, connector updates, carrier/tax/trading-partner rule changes, and configuration updates. Review updates on a schedule and archive only material public-safe history.

## Public-Safe Boundary

Do not publish internal release calendars, customer-specific impact, private vendor notices, account IDs, connector credentials, screenshots, logs, custom scripts, custom workflows, proprietary mappings, tax policy, carrier account terms, or trading partner requirements.

## Review Cadence

Use a regular cadence such as monthly or release-driven review.

Suggested review areas:

- NetSuite release notes and Help Center updates
- Avalara public product, tax, connector, and developer updates
- Pacejet public support or product updates
- SPS Commerce public product, support, and EDI/trading partner update notes
- Connector bundle or integration version changes
- Carrier, tax, or trading partner rule changes that affect public documentation

## Update Classification

Classify each update before changing articles.

### No Documentation Change

Use when:

- Update is unrelated.
- Update is private/account-specific.
- Update does not change public behavior or troubleshooting guidance.

### Current Article Refresh

Use when:

- Public behavior changed.
- Terminology changed.
- Troubleshooting path changed.
- A new common error or workflow should be reflected.

### Historical Note

Use when:

- Old behavior may still matter for older transactions or legacy connector versions.
- The update explains why older screenshots, logs, or support notes differ.
- The behavior is version-specific and no longer belongs in the current article.

### New Article Needed

Use when:

- Update introduces a new workflow, API, connector behavior, or recurring support pattern.
- Existing article would become too broad.
- The topic crosses NetSuite and multiple vendors.

## Review Workflow

1. Collect public update source.
2. Identify affected system: NetSuite, Avalara, Pacejet, SPS Commerce, connector, carrier, tax, or trading partner workflow.
3. Identify affected records or process: customer, item, address, order, fulfillment, invoice, tax, shipment, EDI document, script, workflow, or report.
4. Decide classification: no change, article refresh, historical note, or new article.
5. Update current article first when behavior changed.
6. Add historical note only when old behavior remains useful.
7. Update `CHANGELOG.md`, `BACKLOG.md`, `PROJECT_STATUS.md`, or `KNOWN_GAPS.md` as needed.
8. Keep private implementation details out of public documentation.

## Historical Note Placement

Use the `history/` area for public-safe notes about superseded or version-specific behavior.

Suggested locations:

- `history/netsuite/`
- `history/avalara/`
- `history/pacejet/`
- `history/sps-commerce/`

Historical notes should include:

- Public source or source category
- Date reviewed
- Affected article
- Old behavior summary
- Current behavior pointer
- Public-safe caution if implementation-specific behavior varies

## Impact Review Questions

Ask:

1. Does this update change what users should check first?
2. Does it affect screenshots or error messages users may provide?
3. Does it affect connector timing, writeback, retry, or duplicate risk?
4. Does it affect NetSuite records, fields, statuses, roles, workflows, scripts, or saved searches?
5. Does it affect address, item, tax, shipment, invoice, or EDI mapping behavior?
6. Does the current article need new language, or should this be a historical note?

## AI Assistant Response Pattern

When asked whether documentation needs updating after a vendor release, the assistant should:

1. Identify the affected system and workflow.
2. Check whether the source is public and stable enough to cite or summarize.
3. Classify the update as no change, article refresh, historical note, or new article.
4. Update current guidance before adding history.
5. Keep account-specific behavior and private release notes out of public docs.

## Related Articles

- [Cross-Vendor Support](README.md)
- [NetSuite-Centered Integration Map](netsuite-centered-integration-map.md)
- [Cross-Vendor Incident Intake Checklist](integration-incident-intake-checklist.md)
- [History Area](../../history/README.md)
