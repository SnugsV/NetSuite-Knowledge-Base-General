# Runtime Decision Trees

## Purpose

Reusable decision trees showing how an AI moves between the six layers and supporting frameworks during execution.

## Main Dispatch

```
Customer request received.
  │
  ├── Text: "What is..." / "How do I..." → Question → Layer 1 (Curriculum)
  │
  ├── Text: "Not working" / "Error" / "Broken" / "Failed" → Troubleshooting
  │   └── Module match?
  │       ├── Pacejet → Context (pacejet-context) → Metadata → Skill → Support
  │       ├── Saved Search → Support Intelligence (saved-searches-support)
  │       ├── Inventory → Support Intelligence (inventory-support)
  │       ├── Purchasing → Support Intelligence (purchasing-support)
  │       └── Accounting → Support Intelligence (accounting-support)
  │
  ├── Text: "Need to set up" / "Configure" / "Enable" → Configuration
  │   └── Route: Solution Architect → Context → Metadata → Skill
  │
  ├── Text: "Need a search" / "Report" / "Dashboard" → Reporting
  │   └── Route: Solution Architect → Metadata → Saved Search Builder Skill
  │
  ├── Text: "Need a script" / "Custom code" → SuiteScript
  │   └── Route: Solution Architect (can workflow do this?) → Context → Metadata
  │
  ├── Text: "Need automation" / "Approval" / "Notification" → Workflow
  │   └── Route: Solution Architect (workflow vs. script) → Context → Skill (if exists)
  │
  ├── Text: "Sync" / "Integration" / "Connect" / "Import" → Integration
  │   └── Route: Context → Metadata → Support Intelligence
  │
  └── Text: "Best way to" / "Improve" → Optimization
      └── Route: Layer 1 (current process) + Layer 5 (alternatives)
```

## Confidence Gate

```
After gathering metadata (Step 5):
  │
  ├── All required metadata collected → Confidence = High → Proceed
  │
  ├── Some required + some optional collected → Confidence = Medium
  │   └── Note gaps in recommendation. "This recommendation assumes X."
  │
  ├── Some required, no optional → Confidence = Low
  │   └── Do not proceed. "I need [specific metadata] before I can recommend. Here's why."
  │
  └── No metadata → Confidence = Unknown
      └── Do not proceed. Explain the information-gathering process.
```

## Escalation Gate

```
After diagnosis (Step 7):
  │
  ├── Root cause found, confidence High → Recommend independently
  │
  ├── Root cause found, confidence Medium → Recommend with caveats
  │
  ├── Root cause not found → Escalate
  │   └── Provide: what was checked, what metadata was gathered, remaining unknowns
  │
  ├── Suspected system bug → Escalate to Oracle/Pacejet support
  │   └── Provide: reproduction steps, evidence, affected records
  │
  ├── Requires admin access → Provide instructions for admin
  │
  └── Requires SuiteScript changes → Provide design for developer
```

## Layer Routing Summary

| Situation | Layers to Consult (in order) |
|---|---|
| Question about ERP process | Layer 1 only |
| Troubleshooting: Pacejet | Layer 3 → Layer 6 → Layer 4 → Layer 2 |
| Troubleshooting: ERP module | Layer 3 → Layer 6 → Layer 2 |
| Configuration | Layer 5 → Layer 3 → Layer 6 → Layer 4 |
| Saved Search | Layer 5 → Layer 6 → Layer 4 |
| SuiteScript | Layer 5 → Layer 3 → Layer 6 |
| Integration | Layer 3 → Layer 6 → Layer 2 |
| Training | Layer 1 |
| Optimization | Layer 1 → Layer 5 |