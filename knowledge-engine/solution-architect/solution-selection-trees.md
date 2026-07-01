# Solution Selection Trees

## Purpose

Structured decision trees that guide the AI from a business problem to the recommended NetSuite capability.

## Informational Requirements

The user needs to see data. The question is: in what format, at what frequency, and for what purpose?

### Decision Tree

```
The user needs to see data.
  │
  ├── Is this a one-time question?
  │   ├── Yes → Is the data from a single record type?
  │   │   ├── Yes → SuiteAnalytics Workbook
  │   │   └── No → SuiteAnalytics Workbook (dataset + workbook)
  │   │
  │   └── No → How often will they need this data?
  │       ├── Daily → Saved Search with email schedule
  │       ├── Weekly → Saved Search with email schedule
  │       ├── Monthly → Saved Search
  │       └── Real-time → Dashboard or KPI portlet
  │
  ├── Do they need formatted output (headers, logos, tables)?
  │   ├── Yes → SuiteAnalytics Workbook
  │   └── No → Saved Search
  │
  ├── Do they need to export data?
  │   ├── Yes → Saved Search (CSV export)
  │   └── No → Depends on format above
  │
  ├── Do they need drill-down capability?
  │   ├── Yes → SuiteAnalytics Workbook
  │   └── No → Saved Search
  │
  ├── Do they need charts or visualizations?
  │   ├── Yes → SuiteAnalytics Workbook or Dashboard KPI
  │   └── No → Saved Search
  │
  └── Is this for a dashboard / at-a-glance view?
      ├── Yes → Dashboard portlet using a Saved Search
      └── No → Depends on frequency above
```

### Summary Table

| Requirement | Recommended | Alternative |
|---|---|---|
| One-time analysis | SuiteAnalytics Workbook | Saved Search |
| Daily report | Saved Search (scheduled) | SuiteAnalytics (if formatted) |
| Real-time view | Dashboard / KPI | Saved Search portlet |
| Formatted output | SuiteAnalytics Workbook | CSV export + formatting |
| Charts and drill-down | SuiteAnalytics Workbook | Dashboard |
| Simple list | Saved Search | — |
| Export to CSV | Saved Search | SuiteAnalytics |

---

## Automation Requirements

The user needs a process to happen automatically — routing, notifications, field updates, record creation.

### Decision Tree

```
The user needs automated processing.
  │
  ├── Is this a simple approval or notification?
  │   ├── Yes → Workflow (SuiteFlow)
  │   └── No → See below
  │
  ├── Does it involve:
  │   ├── Field updates on state change → Workflow
  │   ├── Email notifications → Workflow
  │   ├── Record creation from another record → Workflow
  │   ├── Complex logic (30+ conditions) → SuiteScript
  │   ├── External API calls → SuiteScript (RESTlet)
  │   ├── Large batch processing → SuiteScript (Map/Reduce)
  │   └── Real-time processing of incoming data → SuiteScript (RESTlet or User Event)
  │
  └── Does the workflow need to call an external system?
      ├── Yes → SuiteScript (workflows cannot call external systems)
      └── No → Workflow (simplest option)
```

### Workflow vs. SuiteScript

| Factor | Workflow | SuiteScript |
|---|---|---|
| **Complexity of logic** | Simple to moderate | Any complexity |
| **Number of conditions** | Limited (practical) | Unlimited |
| **External calls** | Not supported | Supported |
| **Learning curve** | Low | High |
| **Maintenance** | Low | High |
| **Performance** | Good | Varies |
| **Best for** | Standard automation | Custom business logic |

---

## Integration Requirements

The user needs NetSuite to exchange data with another system.

### Decision Tree

```
The user needs data exchange with another system.
  │
  ├── Is this a one-time data load?
  │   ├── Yes → CSV Import
  │   └── No → See below
  │
  ├── Is this real-time or scheduled?
  │   ├── Real-time → RESTlet or SuiteTalk
  │   └── Scheduled → Map/Reduce or CSV Import
  │
  ├── Is the other system a standard integration?
  │   ├── E-commerce (Shopify, Magento) → Check for native connector or SuiteApp
  │   ├── Bank → Bank feed (native)
  │   ├── Shipping (UPS, FedEx) → Native integration
  │   ├── EDI → SuiteApp or SuiteTalk
  │   └── Custom / Other → RESTlet or SuiteTalk
  │
  ├── What volume of data?
  │   ├── High volume (thousands of records) → Map/Reduce or SuiteTalk
  │   └── Low volume → RESTlet
  │
  └── Does the integration need to be bidirectional?
      ├── Yes → RESTlet or SuiteTalk with sync logic
      └── No → Directional (import or export) is simpler
```

### Integration Method Summary

| Method | Real-time | Batch | Volume | Complexity |
|---|---|---|---|---|
| CSV Import | No | Yes | High | Low |
| RESTlet | Yes | No | Low-Medium | Medium |
| Map/Reduce | No | Yes | High | High |
| SuiteTalk | Yes | Yes | Medium-High | Medium |
| Native Connector | Yes | Yes | Varies | Low |

---

## Configuration Requirements

The user needs to change a setting, enable a feature, or configure a preference.

### Decision Tree

```
The user needs to change a NetSuite setting.
  │
  ├── Can this be done in Setup or Preferences?
  │   ├── Yes → Native Configuration
  │   └── No → See below
  │
  ├── Is this a feature enablement?
  │   ├── Yes → Native Configuration (Setup > Company > Enable Features)
  │   └── No → See below
  │
  ├── Does the standard system need to store more data?
  │   ├── Yes → Custom Fields or Custom Records
  │   └── No → See below
  │
  ├── Does the standard form need to be modified?
  │   ├── Yes → Custom Forms
  │   └── No → See below
  │
  └── Is the requirement outside standard NetSuite?
      ├── Yes → SuiteApp, SuiteScript, or custom integration
      └── No → Re-evaluate — the capability may exist
```

---

## Transactional Requirements

The user needs to create or modify a transaction (sales order, purchase order, journal entry, etc.).

### Decision Tree

```
The user needs to create or modify records.
  │
  ├── Is this a standard transaction type?
  │   ├── Yes → Use the standard transaction
  │   └── No → See below
  │
  ├── Does the standard transaction need additional fields?
  │   ├── Yes → Add custom fields to the transaction
  │   └── No → See below
  │
  ├── Does the standard transaction need different behavior?
  │   ├── Yes → Custom Transaction or SuiteScript
  │   └── No → Use the standard transaction
  │
  └── Is the requirement a completely new transaction type?
      ├── Yes → Custom Transaction (Advanced)
      └── No → Use the closest standard transaction
```

---

## Customization Requirements

The user needs behavior that does not exist in standard NetSuite.

### Decision Tree

```
The user needs custom behavior.
  │
  ├── Does this add a new data field or record?
  │   ├── Yes → Custom Field or Custom Record
  │   └── No → See below
  │
  ├── Does this change how an existing record behaves?
  │   ├── Yes → SuiteScript (User Event)
  │   └── No → See below
  │
  ├── Does this add automated processing?
  │   ├── Simple → Workflow
  │   ├── Complex → SuiteScript
  │   └── External → SuiteScript (RESTlet)
  │
  └── Is there a SuiteApp that already does this?
      ├── Yes → Evaluate SuiteApp (faster, but ongoing cost)
      └── No → Build custom
```

---

## Cross-Requirement Notes

- **Multiple solutions may be valid** — some requirements can be met by several capabilities. Document the trade-offs and let the customer decide.
- **Start simple** — always try the simplest capability first. Configuration before workflow, workflow before scripting.
- **Escalate** — if the simplest option does not meet the requirement, move to the next level.

## Related Documents

- [Capability Reference](capability-reference.md)
- [SOLUTION_ARCHITECT_REASONING.md](SOLUTION_ARCHITECT_REASONING.md)
- [Routing to AI Skills](routing-to-skills.md)