# Problem Classification

## Purpose

Problem classification ensures the AI systematically considers all possible causes before focusing on one domain. Misclassification is the most common reason for incorrect recommendations.

## Classification Categories

| Category | Examples | Keywords |
|---|---|---|
| **Configuration** | Feature not enabled, setting incorrect, preference wrong | "Can't find", "Not available", "Disabled" |
| **Permissions** | User cannot see, cannot access, cannot edit | "Can't see", "Not authorized", "Grayed out" |
| **Customization** | Script error, workflow issue, custom record problem | "Script error", "Custom", "Bundle" |
| **Data Integrity** | Wrong quantity, duplicate record, missing data | "Wrong", "Missing", "Duplicate", "Lost" |
| **Accounting** | GL out of balance, period won't close, wrong COGS | "Close", "Balance", "COGS", "Revenue" |
| **Inventory** | Quantity wrong, can't transfer, cost wrong | "On hand", "Transfer", "Cost", "Count" |
| **Manufacturing** | Work order won't build, BOM wrong, WIP issue | "Build", "BOM", "Work order", "Assembly" |
| **Performance** | System slow, search slow, report timeout | "Slow", "Timeout", "Unresponsive" |
| **Integration** | Sync failure, import error, data mismatch | "Sync", "Import", "Integration", "API" |
| **Workflow** | Workflow not triggering, stuck in a state | "Workflow", "Approval", "Routing" |
| **Script** | Script error, script timeout, unexpected behavior | "Script", "Error code", "SuiteScript" |
| **Reporting** | Wrong numbers, missing data, formula error | "Report", "Search", "Formula", "Results" |
| **User Training** | User does not understand process | "How do I", "Where is", "Never done this" |

## Classification Exercise

When a customer reports a problem, classify it by these steps:

### Step 1: Capture the Exact Statement

Write the customer's exact words. Do not interpret yet.

> Example: "We shipped an order last week but the customer says they never received an invoice."

### Step 2: Map to Primary Category

| Indicator | Primary Category |
|---|---|
| "Shipped" + "no invoice" | Accounting (invoicing) |
| "Error" + "script" | Script |
| "Can't see" + "menu" | Permissions |
| "Slow" + "search" | Performance |

### Step 3: Consider Secondary Categories

- Accounting issue → May also be a configuration issue (invoicing feature not enabled)
- Script error → May also be a customization issue
- Permission issue → May also be a configuration issue (role not set up correctly)

### Step 4: Prioritize

The most likely category should be investigated first. But keep the secondary category in mind if the primary does not yield results.

## Related Documents

- [Customer Interview Framework](customer-interview-framework.md)
- [Solution Confidence](solution-confidence.md)
- [Escalation Intelligence](escalation-intelligence.md)
- [CUSTOMER_CONTEXT_REASONING.md](CUSTOMER_CONTEXT_REASONING.md)