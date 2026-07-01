# Confidence Calibration

## Purpose

Compare predicted confidence against actual outcomes to improve the platform's self-assessment accuracy. Without calibration, confidence scoring may be overconfident (recommending with high confidence that turns out wrong) or underconfident (requiring excessive evidence before acting).

## Calibration Log Template

```
CALIBRATION-[ID]: [Case or pattern reference]

## Predicted Confidence

| Stage | Predicted | Rationale |
|---|---|---|
| Initial triage | (High/Med/Low) | (Why this was the prediction) |
| After metadata | (High/Med/Low) | (Why this was the prediction) |
| Final diagnosis | (High/Med/Low) | (Why this was the prediction) |

## Actual Outcome

| Stage | Outcome | Notes |
|---|---|---|
| Initial diagnosis | (Correct/Partial/Wrong) | (What actually happened) |
| Final diagnosis | (Correct/Partial/Wrong) | (What actually happened) |

## Calibration Result

| Stage | Calibration | Meaning |
|---|---|---|
| Initial triage | (On/Over/Under) | (Overconfident, underconfident, or accurate) |
| After metadata | (On/Over/Under) | (Overconfident, underconfident, or accurate) |
| Final diagnosis | (On/Over/Under) | (Overconfident, underconfident, or accurate) |

## What Influenced the Calibration

What made the prediction inaccurate:
- Missing information that was assumed
- Incorrect assumption about configuration
- Unusual customization not captured in context
- Feature behavior that differed from documentation

## Confidence Adjustment Recommendation

How the Agent Runtime confidence framework should be updated:
```

## Calibration Decision Tree

```
After each case, compare predicted vs. actual:
  │
  ├── Predicted High, Actually Correct → Calibration On. No change needed.
  │
  ├── Predicted High, Actually Wrong → Calibration Over.
  │   What was missed?
  │   ├── Missing metadata → Confidence should be Medium when this metadata is absent
  │   └── Assumed configuration → Confidence should require configuration verification
  │
  ├── Predicted Medium, Actually Correct → Calibration Under (if frequent).
  │   What additional evidence was collected that raised accuracy?
  │   └── This evidence should become a confidence booster
  │
  ├── Predicted Medium, Actually Wrong → Calibration On (correctly uncertain).
  │   What would have raised confidence to High?
  │   └── That information should be added to metadata requirements
  │
  ├── Predicted Low, Actually Correct → Calibration Under.
  │   What confidence factors should have been higher?
  │   └── Adjust confidence rules for this pattern
  │
  └── Predicted Low, Actually Wrong → Calibration On (correctly uncertain).
      └── Possibly unavoidable with available information
```

## Confidence Scoring Trends

Track over time:

| Quarter | Cases | High Conf Correct | High Conf Wrong | Med Conf Correct | Med Conf Wrong | Low Conf Correct | Low Conf Wrong |
|---|---|---|---|---|---|---|---|
| Q1 | N | N | N | N | N | N | N |

Target: > 90% of High confidence predictions should be correct.

## Related Documents

- [Agent Runtime: Confidence Framework](../AGENT_RUNTIME.md#confidence-framework)
- [Agent Runtime: Confidence Degradation Factors](../AGENT_RUNTIME.md#confidence-degradation-factors)
- [Resolution Patterns](resolution-patterns.md)