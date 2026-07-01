---
title: Custom Forms
module: Administration
difficulty: Advanced
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Custom Forms

## Quick Summary

Custom forms are tailored versions of standard NetSuite forms, modified to match specific business processes. Unlike the standard form, which shows all available fields, a custom form can show department-specific fields, hide irrelevant sections, set defaults, and control field behavior.

## Difficulty

Advanced

## Estimated Time

15 minutes

## Overview

While the standard form for a record type includes all fields that exist in the system, custom forms let administrators present a focused view to each group of users. A customer service representative sees a different form for a sales order than an accountant or a warehouse worker.

## Creating a Custom Form

To create a custom form:

1. Navigate to **Setup > Customization > Forms**
2. Click **New** and select the record type
3. Choose whether to start from a standard form or copy an existing custom form
4. Configure the fields, tabs, columns, and layout
5. Assign the form to specific roles
6. Save the form

Starting from a copy of an existing form is recommended — it preserves any customizations already made and reduces the risk of missing a needed field.

## Form Configuration Options

When creating or editing a custom form, you can configure:

### Screen Layout

- **Header fields** — Which fields appear at the top of the form
- **Field order** — The sequence of fields and sections
- **Column configuration** — Which fields appear in each column
- **Tab visibility** — Which tabs are shown or hidden
- **Sublist configuration** — Which sublists appear and their column layout

### Field Properties

- **Mandatory** — Field must be filled in to save
- **Read-only** — Field is displayed but cannot be edited
- **Hidden** — Field exists but is not shown on this form
- **Default value** — A value automatically populated when a new record is created
- **Help text** — Tooltip text shown when the user hovers over the field

### Display Conditions

- **Field display rules** — Show or hide a field based on the value of another field
- **Mandatory conditions** — Make a field required only when certain conditions are met
- **Sublist display rules** — Show or hide entire sublists based on record conditions

## Custom Forms with Custom Segments

Custom segments are classification fields that can be applied across multiple record types. When a custom segment is created, it must be added to forms to be visible to users.

For example, a "Business Unit" custom segment can be added to the Sales Order form, the Purchase Order form, and the Invoice form. Each form's layout determines where the segment appears.

## Form Versions and Auditing

When you modify a custom form, NetSuite saves the changes immediately. There is no version control for forms — previous versions are not automatically preserved.

Best practice is to:

- Test form changes in a sandbox first
- Document what changed and why
- Change the form's name to include a version indicator if necessary (e.g., "Sales Order v2")
- Audit form changes through System Notes or Audit Trail

## Performance Considerations

Forms with many custom fields, display conditions, or complex layouts can affect:

- **Load time** — Forms with many fields take longer to render
- **Save time** — Complex validation rules on fields can slow saving
- **Search performance** - Custom fields used in saved searches may impact search speed

Keep custom forms focused on what users actually need. Avoid the temptation to add every available field "just in case."

## Multi-Level Custom Forms

For organizations with complex structures, multiple custom forms can be created for the same record type:

1. **Basic form** — Minimal fields for data entry clerks
2. **Standard form** — Full fields for departmental users
3. **Advanced form** — All fields for administrators and power users

Each is assigned to the appropriate role. This approach reduces clutter for most users while keeping full functionality accessible.

## Common Mistakes

- **Creating a custom form from scratch instead of copying an existing form**: Starting from scratch means you must manually add all fields, increasing the risk of missing something important.
- **Over-engineering display conditions**: Complex display rules are difficult to maintain and debug. Keep conditions simple.
- **Not assigning the form to any role**: A form with no role assignment is not used by anyone. It appears as an option but is not the default for any user.
- **Removing mandatory standard fields**: Some standard fields are required for system functionality. Removing them from a custom form can cause errors when saving records.

## Best Practices

- Always copy an existing form as a starting point.
- Name custom forms descriptively (e.g., "Sales Order — Inside Sales").
- Assign each custom form to the specific roles that need it.
- Limit display conditions to what is genuinely necessary.
- Test form changes in a sandbox before deploying to production.
- Review custom forms annually and remove or update outdated ones.
- Document significant form changes in the session report.

## Related Articles

- [Forms](forms.md)
- [Roles](roles.md)
- [Permissions](permissions.md)
- [Lists and Records](../getting-started/lists-and-records.md)

## Oracle References

- [Oracle NetSuite Help Center: Custom Forms](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Creating Custom Entry Forms](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)