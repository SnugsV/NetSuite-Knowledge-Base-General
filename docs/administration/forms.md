---
title: Forms
module: Administration
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Forms

## Quick Summary

Forms define how records and transactions appear in NetSuite. Each record type has one or more forms that control which fields are shown, how they are arranged, and which tabs they appear on. Form customization is a core administration task because it directly affects how users interact with the system.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

When a user opens a record in NetSuite — a customer, a sales order, an item — they see a form. The form defines the layout of fields, tabs, and sections. Different roles can have different forms for the same record type, allowing each department to see only what they need.

## Standard Forms vs. Custom Forms

NetSuite provides standard forms for every record type. These cover the most common fields and layouts. Custom forms allow administrators to:

- Add or remove fields from the form
- Rearrange fields and sections
- Create different form layouts for different roles
- Set default values for fields on the form
- Make fields mandatory or optional
- Create sub-tabs and groupings

## Accessing Forms

Forms are managed at:

```
Setup > Customization > Forms
```

From here you can view, create, and edit forms for all record types.

## Form Types

NetSuite supports several form types:

| Form Type | Examples |
|---|---|
| **Transaction Forms** | Sales Order, Purchase Order, Invoice, Credit Memo |
| **Record Forms** | Customer, Vendor, Item, Employee |
| **Entry Forms** | Journal Entry, Inventory Adjustment |
| **List Forms** | Custom record forms |

## Form Layout

A form is organized into these elements:

| Element | Description |
|---|---|
| **Header** | Fields at the top of the form — typically key identifying information |
| **Tabs** | Sections that organize related fields (e.g., "Shipping," "Financial," "Classification") |
| **Columns** | Fields arranged in columns within a tab |
| **Sublists** | Tables of related records (e.g., line items on a sales order) |
| **Footer** | Total fields, approval buttons, action buttons |

## Fields on Forms

Forms can include:

- **Standard fields** — Built-in NetSuite fields that come with every form
- **Custom fields** — Fields created by administrators to capture organization-specific data
- **Mandatory fields** — Fields that must be filled in before the record can be saved
- **Read-only fields** — Fields that are displayed but cannot be edited
- **Hidden fields** — Fields that exist on the record but are not shown on this form

## Custom Fields

Custom fields are the primary way organizations extend NetSuite to capture their specific data. They are created at:

```
Setup > Customization > Fields > New

Custom fields can be:

- **Free-form text** — Single line or multi-line text input
- **Select** — Dropdown list of options
- **Date** — Date picker
- **Currency** — Monetary value
- **Checkbox** — Yes/no value
- **Formula** — Calculated value based on other fields

When creating a custom field, you select which forms it appears on. A field that is not added to any form exists on the record but is invisible to users.
```

## Assigning Forms to Roles

Forms can be assigned to specific roles:

1. Create or edit the form
2. Go to the **Roles** subtab
3. Select which roles should use this form
4. If no roles are selected, the form is available as an option for all roles

When a user opens a record, NetSuite checks which form is assigned to their role and displays that form. If no form is specifically assigned, the default form for that record type is used.

## Form Preferences

Users can set their preferred form from their personal preferences:

```
Home > Set Preferences > Print/Mail > Form
```

This overrides the default form for that specific user, regardless of role.

## Common Mistakes

- **Creating too many custom fields**: Each custom field adds complexity. Only create fields that are actually needed.
- **Not assigning forms to roles**: Without role assignment, all users see the same form. Role-specific forms are what make customization valuable.
- **Making fields mandatory unnecessarily**: Mandatory fields slow down data entry. Only require fields that are genuinely needed for every record.
- **Deleting a form that is in use**: Before deleting a form, verify that no roles are using it and no users have it as their preference.

## Best Practices

- Start with standard forms and customize only what is needed.
- Create role-specific forms rather than a single form for all users.
- Name custom forms clearly (e.g., "Sales Order — Customer Service").
- Test form changes in a sandbox before deploying to production.
- Review custom fields periodically and deactivate unused ones.
- Document why each custom field was created.

## Related Articles

- [Custom Forms](custom-forms.md)
- [Roles](roles.md)
- [Permissions](permissions.md)
- [Lists and Records](../getting-started/lists-and-records.md)

## Oracle References

- [Oracle NetSuite Help Center: Forms](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Customizing Forms](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)