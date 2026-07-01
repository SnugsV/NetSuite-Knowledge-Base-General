# Knowledge Gap Analysis

## Purpose

Systematically identify missing documentation, AI Skills, metadata requirements, and support patterns based on completed cases.

## Gap Analysis Process

```
Completed Case
       ↓
Identify what was missing during the engagement
       ↓
Categorize the gap
       ↓
Prioritize by frequency and impact
       ↓
Recommend repository update
```

## Gap Categories

| Category | Description | Example |
|---|---|---|
| **Missing module** | An entire documentation module does not exist | No Pacejet integration docs before PR #19 |
| **Missing support pattern** | A common issue is not covered in support intelligence | Label troubleshooting was not structured |
| **Missing AI Skill** | No executable skill exists for this task | Rate troubleshooting skill |
| **Missing metadata** | A required metadata item is not documented | Script execution log not listed as required |
| **Missing context** | A customer context element is not defined | Bundle version not in Pacejet context |
| **Missing configuration** | A configuration pattern is not documented | ASD field mapping during setup |
| **Stale documentation** | Existing documentation is out of date | Project tracking files showing v0.2.2 |

## Gap Prioritization

| Priority | Criteria | Action |
|---|---|---|
| **Critical** | Affects > 20% of cases, causes incorrect diagnosis | Create immediately |
| **High** | Affects 10-20% of cases, significantly increases resolution time | Create this sprint |
| **Medium** | Affects 5-10% of cases, moderately increases resolution time | Create next sprint |
| **Low** | Affects < 5% of cases, minor impact | Create as time allows |

## Gap Log Template

```
GAP-[ID]: Descriptive Title

## Category

(Missing module / Missing support pattern / Missing AI Skill / Missing metadata / Missing context / Missing configuration / Stale documentation)

## Evidence

How many cases encountered this gap:
What impact did the gap have:
- Increased resolution time by: (time estimate)
- Caused incorrect initial diagnosis: (yes/no)
- Required escalation that could have been avoided: (yes/no)

## Priority

(Critical / High / Medium / Low)

## Recommended Action

What should be created or updated:
Repository location:
Estimated effort:

## Status

(Open / In Progress / Complete)

## Related Cases

CASE-[IDs]:
```

## Common Gap Patterns

| Pattern | Likely Root Cause | Prevention |
|---|---|---|
| Customer context incomplete | Missing context template | Review context templates after each engagement |
| Metadata requirement missing | New feature or integration | Update metadata documents when new features are used |
| Support pattern not documented | Unusual error combination | Log unusual errors for pattern extraction |
| AI Skill does not exist | New task type | Assess new task types for skill creation |
| Documentation stale | Content drift from releases | Run Knowledge Intelligence Pipeline |