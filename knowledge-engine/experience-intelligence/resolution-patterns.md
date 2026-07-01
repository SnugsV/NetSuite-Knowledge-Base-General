# Resolution Patterns

## Purpose

Extract recurring solution patterns from completed cases. Over time, patterns emerge that indicate common root causes, effective diagnostic paths, and confidence trends.

## Pattern Template

```
PATTERN-[ID]: [Pattern Name]

## Symptoms

[Common customer-reported symptoms]
- Symptom 1
- Symptom 2

## Most Common Root Cause

[The root cause that appears most frequently for these symptoms]

## Other Possible Causes (by frequency)

1. [Most frequent]
2. [Second most frequent]
3. [Third most frequent]

## Recommended Investigation Order

1. [First thing to check — the most productive path]
2. [Second thing]
3. [Third thing]

## Confidence Trend

| Symptoms | Rate of Accurate Diagnosis | High Confidence When... |
|---|---|---|

## Effectiveness Score

How often this pattern leads to a correct diagnosis: [%]

## Related Cases

[CASE-IDs]

## Documentation

Where this pattern is documented in the repository:
```

## Example Pattern

```
PATTERN-001: Label Generation Failures — Address Validation

## Symptoms
- "The label won't generate"
- Error code starting with "AV" (AV1004, AV1005, AV1008, AV2202)
- Error occurs on specific addresses but not others

## Most Common Root Cause
Address validation failure — the address does not match the carrier's database.

## Other Possible Causes (by frequency)
1. Address validation failure (65%)
2. Missing package data — weight or dimensions (20%)
3. Carrier contract issue (10%)
4. Label connector configuration error (5%)

## Recommended Investigation Order
1. Check the error code — AV prefix confirms address validation
2. Verify the address on the carrier's website directly
3. Check for common address issues (PO Box, insufficient street data, international format)
4. If address validates on carrier site but not in Pacejet, check Pacejet address database

## Confidence Trend
| Symptoms | Diagnosis Accuracy | High Confidence When |
|---|---|---|
| AV error code present | 95% | Error code + address confirmed correct on carrier site |
| No error code, but label fails | 70% | Package data verified + carrier active |

## Effectiveness Score
85% — most label failures with AV error codes are resolved by correcting the address.

## Documentation
- pacejet-support.md: Label generation case
- pacejet-label-troubleshooter.md: Step 1 — check error message
- troubleshooting-case-library.md: Case 1
```

## Pattern Maintenance

| Action | Frequency |
|---|---|
| Review new cases and extract patterns | Monthly |
| Update pattern effectiveness scores | Quarterly |
| Archive patterns with < 2 occurrences | Annually |
| Promote high-confidence patterns into AI Skills | As validated |