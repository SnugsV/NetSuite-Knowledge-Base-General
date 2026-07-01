# Saved Search Metadata

## Purpose

Defines exactly what metadata must be collected before designing a Saved Search. Without this metadata, the AI may build a search that returns incorrect results or does not match the customer's environment.

## Required Metadata

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Record type** | The foundation of the search — wrong record type returns wrong data | Ask: "What type of records are you searching for?" |
| **Internal field IDs** | Formulas require internal IDs (e.g., `{amount}`, not "Amount") | Request a Record Browser export for the record type |
| **Desired output columns** | Determines Results tab configuration | Ask: "What fields should appear in the results?" |
| **Existing similar searches** | Avoids duplicating existing work; the search may already exist | Ask: "Do you have any existing saved searches for this?" |
| **User role** | Determines which records and fields the user can see | Ask: "What role will run this search?" |
| **OneWorld status** | Changes how subsidiary and intercompany fields are available | Ask: "Do you use OneWorld?" |

## Optional Metadata

| Metadata Item | Why It Matters | How to Collect |
|---|---|---|
| **Sample data export** | Validates the search results match expectations | Run an existing similar search and export to CSV |
| **Screenshots of desired output** | Confirms the AI understands what the user wants | Ask: "Can you sketch or screenshot what you want to see?" |
| **Frequency and schedule** | Determines whether email scheduling is needed | Ask: "How often will you run this?" |
| **Existing report that almost works** | Saves time by modifying an existing report | Ask: "Is there an existing report that is close to what you need?" |
| **Filter criteria** | Defines what data should be included vs. excluded | Ask: "What conditions should the data meet?" |

## Nice-to-Have Metadata

| Metadata Item | Why It Matters |
|---|---|
| **Custom field definitions** | Custom fields may have validation rules that affect search behavior |
| **Workflow information** | Workflows may change record status after criteria are checked |
| **User training level** | Determines how much explanation is needed |
| **Integration activity** | External systems may create records that appear in search results |

## Validation Checklist

- [ ] Record type confirmed (e.g., Sales Order vs. Transaction)
- [ ] Internal field IDs verified from Record Browser or custom field list
- [ ] User role confirmed for the target user
- [ ] OneWorld status (if applicable) confirmed
- [ ] Existing searches checked for duplicates
- [ ] Sample data reviewed if available
- [ ] Desired output format confirmed (list, summary, scheduled, CSV)

## Common Metadata Gaps

| Gap | Impact | Recovery |
|---|---|---|
| Record type guessed | Search returns no results or wrong data | Confirm the exact transaction or list type |
| Field IDs assumed | Formula returns blank or error | Request Record Browser export |
| Role not verified | User cannot see expected results | Confirm the user's role and permissions |
| OneWorld status unknown | Subsidiary fields may not work as expected | Ask: "Do you use OneWorld or have multiple subsidiaries?" |
| Existing search not checked | Duplicate work, or the search already exists | Ask about existing searches before building |

## Confidence Impact

| Metadata Collected | Confidence |
|---|---|
| All required + most optional | High |
| All required + some optional | Medium |
| Some required + no optional | Low |
| Required metadata missing | Unknown — do not proceed |

## Related Documents

- [METADATA_REASONING.md](METADATA_REASONING.md)
- [Saved Search Builder Skill](../ai-skills/saved-search-builder.md)
- [Saved Search Support](../support-intelligence/saved-searches-support.md)