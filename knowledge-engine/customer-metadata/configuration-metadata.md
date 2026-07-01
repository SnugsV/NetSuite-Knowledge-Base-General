# Configuration Metadata

## Purpose

Defines exactly what metadata must be collected before designing or modifying custom records, custom fields, custom segments, forms, or roles and permissions. Configuration changes affect the entire system and can be difficult to reverse.

## Required Metadata

### Custom Records

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Purpose of the custom record** | Prevents creating records that already exist or overlap | Ask: "What business data are you trying to capture?" |
| **Existing custom records** | Avoids duplicating existing functionality | Request custom record list |
| **Parent record relationship** | Determines how the custom record relates to standard records | Ask: "How does this data relate to existing NetSuite records?" |
| **Standard records that could be used instead** | Uses standard functionality before customizing | Review available standard records |

### Custom Fields

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Field type required** | Free text, list/select, checkbox, date, currency — each has different behavior | Ask: "What type of data does this field need to store?" |
| **Record type and form assignment** | Custom fields must be assigned to forms to be visible | Ask: "Which record type does this field belong to?" |
| **Existing similar fields** | Avoids creating duplicate or overlapping fields | Request custom field list for the record type |
| **Validation requirements** | Mandatory, unique, formula, or conditional display | Ask: "Are there any rules about when this field should be visible or required?" |

### Custom Segments

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Segment purpose** | Classifications used across record types | Ask: "What are you trying to classify or group?" |
| **Record types to apply** | Segments apply to multiple record types | Ask: "Which records should use this classification?" |
| **Existing similar segments** | Avoids creating overlapping classifications | Request custom segment list |

### Forms

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Current form being used** | Modifications start from the current form | Ask: "What form is the user currently using?" |
| **Fields to add/remove/reorder** | Defines the form change requirements | Ask: "What should change on the form?" |
| **User role for the form** | Different roles may use different forms | Ask: "Which roles use this form?" |
| **Standard vs. custom form** | Standard forms cannot be edited; a custom form must be created | Check if the form is standard or custom |

### Roles and Permissions

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Current role or roles affected** | Changes must be scoped to the correct role | Ask: "Which role needs to be modified?" |
| **Specific permission needed** | Permissions control transaction, list, and report access | Ask: "What specific action is the user unable to perform?" |
| **OneWorld or subsidiary role considerations** | OneWorld roles have subsidiary-level permission settings | Ask: "Does this role need access to specific subsidiaries?" |
| **Existing roles as reference** | An existing role with similar permissions can serve as a template | Ask: "Is there a role that already has the permissions you need?" |

## Optional Metadata

| Metadata Item | Why It Matters |
|---|---|
| **Custom record field list** | Helps identify required vs. optional fields |
| **Permission impact analysis** | Identifies which roles may be affected by form or field changes |
| **Workflow integration** | Workflows may reference custom fields or custom records |
| **Script integration** | Scripts may reference custom fields by internal ID |

## Validation Checklist

- [ ] Custom record purpose confirmed, standard record option evaluated
- [ ] Existing similar fields/records/segments reviewed
- [ ] Field type and validation requirements confirmed
- [ ] Form assignment and role access confirmed
- [ ] Permission changes scoped to the correct role
- [ ] OneWorld settings confirmed (if applicable)

## Common Metadata Gaps

| Gap | Impact | Recovery |
|---|---|---|
| Standard record option not evaluated | Custom record created when a standard record would work | Review standard records before customizing |
| Field type assumed | Cannot change field type after data exists | Confirm field type before creation |
| Form assignment missed | Custom field created but not visible on any form | Assign the field to the appropriate form |
| Role not scoped | Permission change affects unintended users | Scope changes to the specific role |
| Existing customizations not reviewed | Duplicate fields or records created | Review existing customizations before creating |

## Confidence Impact

| Metadata Collected | Confidence |
|---|---|
| All required + existing customizations reviewed | High |
| All required + some optional | Medium |
| Existing customizations not reviewed | Low |
| Required metadata missing | Unknown — do not proceed |

## Related Documents

- [METADATA_REASONING.md](METADATA_REASONING.md)
- [Customer Context: Customizations](../customer-context/customizations.md)
- [Customer Context: NetSuite Configuration](../customer-context/netsuite-configuration.md)