---
title: Company Preferences
module: Administration
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Company Preferences

## Quick Summary

Company preferences control account-wide behavior — date formats, time zones, email defaults, communication templates, and feature-level defaults. These settings affect every user in the account.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

While company setup defines the identity of the organization, company preferences define how NetSuite behaves for that organization. Preferences control everything from how dates are displayed to how email is sent to what default values appear on transactions.

Company preferences are accessible from:

```
Setup > Company > Company Preferences
```

## Preference Categories

### General Preferences

| Preference | What It Controls |
|---|---|
| Date Format | How dates appear on records and reports (MM/DD/YYYY vs DD/MM/YYYY) |
| Time Zone | The account's default time zone |
| Number Format | Decimal separators, grouping symbols, negative number display |
| Email Encoding | Character set for outbound emails |
| Default Country | Country pre-selected on address fields |
| Language | Default language for the account interface |

### Email Preferences

- **Send From** — The default email address for system notifications
- **Email Signature** — Default signature appended to system emails
- **Email Template** — The default email template for customer communications
- **CC/BCC Defaults** — Default addresses to copy on outbound emails

### Transaction Preferences

| Preference | What It Controls |
|---|---|
| Default Order Status | Status applied to new sales orders |
| Default Item Fulfillment Choice | Whether fulfillment is automatic or manual |
| Auto-Allocate Payments | Whether payments are automatically applied to outstanding invoices |
| Show Item Images on Transactions | Whether item images appear on printed forms |

### Communication Preferences

- **Default Communication Template** — The default template for customer correspondence
- **Automatic Email on Transaction Status Change** — Whether customers are automatically notified
- **Attach Files to Emails by Default** — Whether file attachments are included by default

## Account-Level vs. User-Level Preferences

Some preferences can be set at both the account level and the user level:

| Preference | Account Setting | User Override |
|---|---|---|
| Date Format | Default for all users | Each user can set their preference |
| Time Zone | Default for all users | Each user can set their preference |
| Language | Default for all users | Each user can set their preference |
| Email Signature | Default for all users | Each user can set their own signature |
| Email Format (HTML vs Plain) | Account default | Each user can set their preference |

User preferences are set from **Home > Set Preferences**.

## Communication Templates

Communication templates define the format of emails, letters, and faxes sent from NetSuite. Templates can include merge fields that pull data from records automatically.

Common uses:

- **Order confirmations** — Sent to customers when an order is placed
- **Invoice templates** — Define the layout of printed invoices
- **Shipping notifications** — Notify customers when orders ship
- **Password reset emails** — Define the format of password reset messages

Templates are managed at:

```
Setup > Company > Communication Templates
```

## Custom Preferences

Administrators can create custom company preferences using custom segments or custom fields on the company record. These are useful for settings that are specific to the organization's business processes.

## Common Mistakes

- **Setting user-level preferences at the account level**: Some preferences are meant to be user-specific. Setting them at the account level forces the same experience on all users, reducing personalization.
- **Ignoring time zone settings**: If your organization spans multiple time zones, the account-level time zone affects how dates and times appear on records. Users should set their local time zone in their personal preferences.
- **Not testing email preferences**: Email defaults that are configured incorrectly can result in transactional emails not being delivered or being sent from unexpected addresses.
- **Assuming preferences apply to all modules**: Some preferences only affect specific modules or transaction types. Check the scope of a preference before assuming it applies everywhere.

## Best Practices

- Review company preferences during initial setup and after each major NetSuite release.
- Set account-level defaults that make sense for the majority of your users.
- Train users to set their personal preferences (time zone, date format, language) on their first day.
- Test email configuration with a small group before rolling out to all users.
- Document custom preferences and why they were created.

## Related Articles

- [Company Setup](company-setup.md)
- [Enabled Features](enabled-features.md)
- [Administration Overview](administration-overview.md)
- [Personalization](../getting-started/personalization.md)

## Oracle References

- [Oracle NetSuite Help Center: Company Preferences](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)