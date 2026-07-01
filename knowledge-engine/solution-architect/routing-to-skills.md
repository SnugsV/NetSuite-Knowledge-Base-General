# Routing to AI Skills

## Purpose

Once the Solution Architect has determined the correct NetSuite capability, the request routes to the appropriate AI Skill for execution. This document defines the routing rules.

## Capability-to-Skill Mapping

| Selected Capability | AI Skill | Skill Exists? |
|---|---|---|
| Saved Search | [Saved Search Builder](../ai-skills/saved-search-builder.md) | ✅ |
| SuiteAnalytics Workbook | (planned) | 🔜 |
| Workflow (SuiteFlow) | (planned) | 🔜 |
| SuiteScript | (planned) | 🔜 |
| RESTlet | (planned) | 🔜 |
| Map/Reduce | (planned) | 🔜 |
| CSV Import | (planned) | 🔜 |
| SuiteTalk | (planned) | 🔜 |
| Configuration | (planned) | 🔜 |

## Routing Decision Tree

```
Has the Solution Architect recommended a capability?
  │
  ├── Yes → Does an AI Skill exist for this capability?
  │   ├── Yes → Route to the AI Skill for execution
  │   │   - Pass: business objective, customer context, metadata
  │   │   - Expected: execution plan, validation, explanation
  │   │
  │   └── No → Execute without AI Skill guidance
  │       - Use the Capability Reference for best practices
  │       - Document the execution steps
  │       - Escalate if the capability requires expertise beyond AI scope
  │
  └── No → Return to Solution Architect reasoning
      - Gather more customer context
      - Navigate the selection trees again
```

## Information to Pass to AI Skills

When routing from Solution Architect to an AI Skill, include:

| Information | Source |
|---|---|
| **Business objective** | Solution Architect Step 1 |
| **Requirement classification** | Solution Architect Step 2 |
| **Recommended capability** | Solution Architect Step 3-4 |
| **Customer context** | Customer Context Framework |
| **Key constraints** | Budget, timeline, user skills |
| **Success criteria** | What the customer identified as success |

## Skill Execution Flow

```
Solution Architect recommends: Saved Search
  ↓
Route to: Saved Search Builder Skill
  ↓
Skill receives:
  - Business objective: "Monitor overdue POs daily"
  - Requirement: Informational, recurring
  - Customer context: Distribution company, 200 POs/month
  - Success criteria: Daily email with overdue POs
  ↓
Skill executes:
  - Step 1: Confirm saved search is appropriate → Yes
  - Step 2: Gather context → Use above
  - Step 3: Collect metadata → PO fields, user permissions
  - ...
  - Step 11: Consider alternatives → Dashboard? No, need email.
  ↓
Deliverable: Saved search "Overdue POs" with daily email schedule
```

## When an AI Skill Does Not Exist

If the recommended capability has no AI Skill, the AI should:

1. Read the [Capability Reference](capability-reference.md) for the selected capability
2. Use [Support Intelligence](../support-intelligence/README.md) patterns where applicable
3. Document the execution approach clearly
4. Escalate if the capability requires specialized expertise

## Related Documents

- [SOLUTION_ARCHITECT_REASONING.md](SOLUTION_ARCHITECT_REASONING.md)
- [Capability Reference](capability-reference.md)
- [AI Skills](../ai-skills/README.md)
- [Support Intelligence](../support-intelligence/README.md)