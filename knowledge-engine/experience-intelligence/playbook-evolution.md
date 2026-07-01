# Playbook Evolution

## Purpose

How completed work feeds back into the platform's reasoning layers. Every case should improve the platform for the next customer.

## Evolution Flow

```
Case completed
       ↓
Lessons learned captured
       ↓
Gaps identified
       ↓
Recommendations for each framework layer
       ↓
Changes reviewed and applied
       ↓
Platform improves
```

## Layer-Specific Evolution

### Layer 1 — ERP Curriculum

| Input from Experience | Action |
|---|---|
| Common misunderstanding identified | Add or update FAQ, common mistakes, or business example |
| Missing module topic identified | Create or expand the relevant article |
| Feature behavior changed | Update documentation to reflect new behavior |

**Trigger**: When a case reveals that existing documentation is incomplete, misleading, or outdated.

### Layer 2 — Support Intelligence

| Input from Experience | Action |
|---|---|
| New troubleshooting pattern identified | Add pattern to the relevant support document |
| Existing pattern ineffective | Update pattern with corrected investigation order |
| Escalation criteria too broad or narrow | Adjust escalation thresholds |

**Trigger**: When a case confirms, contradicts, or extends an existing support pattern.

### Layer 3 — Customer Context

| Input from Experience | Action |
|---|---|
| Missing context element identified | Add to the relevant context document |
| Context element not useful | Downgrade from required to optional |
| New customization type discovered | Add to customizations documentation |

**Trigger**: When a case reveals that required context was missing or unnecessary.

### Layer 4 — AI Skills

| Input from Experience | Action |
|---|---|
| Skill step missing or incorrect | Update the skill document |
| New skill needed | Create a new skill for the recurring task |
| Skill validation criteria insufficient | Add validation steps |

**Trigger**: When a case follows a skill but reaches an incorrect conclusion.

### Layer 5 — Solution Architect

| Input from Experience | Action |
|---|---|
| Wrong capability selected | Update selection tree or capability evaluation |
| Alternative approach not considered | Add to alternative considerations |
| Feature behavior not as documented | Update capability reference |

**Trigger**: When a case reveals the wrong capability was chosen initially.

### Layer 6 — Customer Metadata

| Input from Experience | Action |
|---|---|
| Missing metadata requirement | Add to required or optional metadata |
| Metadata not useful | Downgrade from required to optional |
| New metadata source discovered | Add collection method |

**Trigger**: When a case shows that missing metadata increased resolution time.

### Agent Runtime

| Input from Experience | Action |
|---|---|
| Dispatch classification incorrect | Update classification rules |
| Confidence score calibration off | Adjust confidence framework |
| Interaction pattern missing | Add new interaction pattern |

**Trigger**: When a case reveals that the runtime made an incorrect decision about how to process the request.

### Knowledge Pipeline

| Input from Experience | Action |
|---|---|
| Source changed | Update source registry |
| Monitoring method ineffective | Update monitoring strategy |
| Report template incomplete | Update KI report template |

**Trigger**: When the Knowledge Intelligence Pipeline misses a source change or generates an incomplete report.

## Evolution Review Cycle

| Frequency | Activity |
|---|---|
| **Weekly** | Review new cases for urgent gaps |
| **Monthly** | Extract resolution patterns, update confidence calibration |
| **Per Sprint** | Review knowledge gaps, create or update documents |
| **Quarterly** | Full playbook review, archive obsolete patterns |

## Case-to-Playbook Example

```
Case: Missing tracking numbers — ASD field not mapped

Lessons learned:
- Assumed ASD fields were correctly configured
- Script execution log should be required metadata
- No support pattern existed for "ASD field mapping" issues

Playbook updates:
1. Support Intelligence: Add "ASD field not mapped" pattern
2. Metadata: Add script execution log to required metadata
3. AI Skill: Add ASD field verification step to label troubleshooter

Result: Next customer with tracking issues gets correct diagnosis
in fewer steps, with higher confidence, and faster resolution.
```

## What Cannot Be Learned From Cases

| Input | Why |
|---|---|
| Customer-identifying information | Not stored. Cases are anonymized. |
| Specific pricing or contract terms | Business-sensitive. Do not capture. |
| Proprietary business processes | Competitively sensitive. Do not capture. |
| Personally identifiable information | Regulatory requirement. Do not capture. |

## Related Documents

- [Case Template](case-template.md)
- [Resolution Patterns](resolution-patterns.md)
- [Knowledge Gap Analysis](knowledge-gap-analysis.md)
- [Confidence Calibration](confidence-calibration.md)
- [Agent Runtime](../AGENT_RUNTIME.md)