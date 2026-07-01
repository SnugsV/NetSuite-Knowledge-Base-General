---
title: Company Setup
module: Administration
difficulty: Beginner
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Company Setup

## Quick Summary

Company setup is the initial configuration of a NetSuite account — defining the company name, address, tax information, base currency, fiscal calendar, and account type. These settings form the foundation that all other configuration builds on.

## Difficulty

Beginner

## Estimated Time

10 minutes

## Overview

When a NetSuite account is first provisioned, it contains minimal configuration. The company setup process defines the fundamental characteristics of the organization: what it is called, where it operates, what currency it uses, and how its financial periods are structured.

Most company setup is done once at account creation and rarely changes afterward.

## Company Information

The Company Information page contains the basic identity of the account:

```
Setup > Company > Company Information
```

Key fields:

| Field | Purpose |
|---|---|
| Company Name | The legal name of the organization. Appears on forms, reports, and email communications. |
| Legal Name | The full legal entity name, which may differ from the trading name. |
| Tax ID / VAT Number | Used for tax reporting on transactions. |
| Address | The primary business address. Used on invoices and other legal documents. |
| Base Currency | The primary currency for the account. This can be changed later but with significant effort. |
| Email | The default from address for system-generated emails. |

## Base Currency

The base currency is one of the most consequential decisions during company setup. NetSuite records all financial transactions in the base currency. If your organization operates in multiple currencies, you can enable the Multi-Currency feature later, but the base currency remains the primary reporting currency.

Changing the base currency after transactions have been recorded requires a CSV import process and can affect historical reporting.

## Fiscal Calendar

NetSuite uses fiscal periods to organize financial transactions. The fiscal calendar defines:

- **Period types** — Monthly, quarterly, or custom
- **Period names** — How periods are labeled (e.g., "Jan 2026" or "Period 01")
- **First period start date** — When the fiscal year begins
- **Year-end closing** — Procedures for closing periods

Fiscal periods are configured at:

```
Setup > Accounting > Manage Accounting Periods
```

## Accounting Periods

Accounting periods control when transactions can be posted. Key concepts:

- **Open period** — Transactions can be created and posted
- **Locked period** — Transactions can be added but not edited or deleted after locking
- **Closed period** — No transactions can be posted

Periods are typically opened and closed on a schedule (e.g., close last month's period on the 5th of this month).

## Tax Setup

Tax configuration depends on the account's country and the features enabled:

- **Tax types** — Sales tax, VAT, GST, or no tax configuration
- **Tax codes** — Specific tax rates applied to transactions
- **Nexus** — Locations where the business has a tax obligation
- **Tax scheduling** — Default tax codes by item, customer, or location

Tax setup is located at:

```
Setup > Accounting > Tax > Set Up Tax
```

## Subsidiaries (OneWorld)

If the account uses NetSuite OneWorld (the multi-subsidiary edition), subsidiaries must be defined during setup. Each subsidiary can have its own:

- Legal name and tax ID
- Base currency
- Fiscal calendar
- Tax configuration
- Intercompany relationships

Subsidiary setup is located at:

```
Setup > Company > Subsidiaries
```

## Common Mistakes

- **Choosing the wrong base currency**: Changing the base currency after transactions exist is complex. Choose carefully during initial setup.
- **Not configuring tax before transactions are created**: If tax settings are incomplete, transactions may have incorrect tax calculations that are difficult to correct retroactively.
- **Leaving accounting periods open indefinitely**: Periods that are never closed make the audit trail harder to navigate and increase the risk of unauthorized changes to historical transactions.
- **Using the company name as the legal name when they differ**: If your trading name differs from your legal entity, use the correct field for each.

## Best Practices

- Set up company information completely before creating any transactions.
- Choose the base currency carefully — it is difficult to change later.
- Close accounting periods on a regular schedule (monthly or quarterly).
- Document the initial company setup decisions, especially base currency, tax configuration, and period definitions.

## FAQ

### Can I change the company name after setup?

Yes. The company name can be updated at any time from Setup > Company > Company Information.

### Can I change the base currency later?

Yes, but it requires a data migration process. It is much easier to choose correctly during initial setup.

### What if my company operates in multiple countries?

You need NetSuite OneWorld (the multi-subsidiary edition) to manage multiple legal entities, currencies, and tax regimes in a single account.

## Related Articles

- [Administration Overview](administration-overview.md)
- [Company Preferences](company-preferences.md)
- [Enabled Features](enabled-features.md)
- [NetSuite Editions](../getting-started/netsuite-editions.md)

## Oracle References

- [Oracle NetSuite Help Center: Company Information](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Setting Up Company Information](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)