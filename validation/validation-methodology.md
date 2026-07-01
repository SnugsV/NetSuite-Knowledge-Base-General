# Validation Methodology

## Purpose

How benchmarks are executed, evaluated, and scored. This methodology ensures consistent, repeatable, and objective validation across all benchmarks and AI models.

## The Validation Process

```
1. Select benchmark
       ↓
2. Run benchmark (AI processes the scenario)
       ↓
3. Record AI response (complete transcript)
       ↓
4. Score using Consultant Scorecard
       ↓
5. Compare to Gold Standard
       ↓
6. Identify gaps
       ↓
7. Report score
       ↓
8. Recommend improvements
```

## Step 1: Benchmark Selection

Select one or more benchmarks from the [Benchmark Catalog](benchmark-catalog.md) that match the capability being validated.

## Step 2: Benchmark Execution

The AI receives only the Business Scenario and Task from the benchmark. The AI does NOT see:
- Expected reasoning path
- Gold standard solution
- Evaluation criteria
- Consultant scorecard dimensions

This simulates a real customer interaction where the AI must apply knowledge from the repository.

## Step 3: Transcript Recording

Every response must be recorded in full, including:
- All questions the AI asked the evaluator
- All metadata the AI requested
- The reasoning process (if the AI explains it)
- The final recommendation

## Step 4: Scoring

Score each dimension on the [Consultant Scorecard](consultant-scorecard.md) based on the transcript.

| Scoring Rule | Description |
|---|---|
| **Evidence-based** | Score based on what the AI actually did, not what it should have done |
| **Blind to gold standard** | Score the response independently before comparing to gold standard |
| **2+ evaluators** | For certification-grade evaluations, use multiple evaluators and average scores |
| **Discrepancy resolution** | If evaluator scores differ by > 2 points on any dimension, discuss and reach consensus |

## Step 5: Gold Standard Comparison

After scoring, compare the AI's response to the Gold Standard:

| Finding | Action |
|---|---|
| Response matches gold standard closely | High confidence in capability |
| Response differs but is still correct | The approach may be valid; evaluate for acceptance |
| Response differs and is incorrect | Identify the gap, recommend framework improvement |
| Response misses key information | Add missing metadata or context to the framework |

## Step 6: Gap Analysis

If the AI missed information, made incorrect assumptions, or chose the wrong solution, determine what caused the gap:

| Gap | Likely Cause | Framework Fix |
|---|---|---|
| Missing metadata not requested | Metadata document does not list it | Update metadata document |
| Wrong capability chosen | Solution Architect selection tree incomplete | Update selection tree |
| Incorrect diagnostic path | Support Intelligence pattern missing | Add support pattern |
| Confidence mismatched | Confidence framework missing degradation factor | Update confidence framework |

## Step 7: Reporting

Each validation produces a Validation Report:

```
VALIDATION-[BENCHMARK-ID]: [Date]

Model: [AI model used]
Framework version: [Repository version]
Benchmark: [Benchmark title]

Consultant Score: [Score]/100
[Link to detailed scorecard]

Gold Standard Comparison: (Match / Acceptable difference / Gap identified)

Gaps Found:
- [Gap 1]
- [Gap 2]

Framework Improvements Recommended:
- [Improvement 1]
- [Improvement 2]

Overall: (Pass / Conditional Pass / Fail)
```

## Step 8: Improvement

If the AI fails any benchmark:

1. Identify the root cause (gap analysis)
2. Update the relevant framework layer
3. Re-run the benchmark
4. Confirm the fix improves the score
5. Document the improvement in the Experience Intelligence Framework

## Scoring Consistency Rules

| Rule | Purpose |
|---|---|
| Use the full 1-10 scale | Prevents grade inflation |
| Score the process, not the outcome | A correct answer through flawed reasoning scores lower |
| Document every score with evidence | Enables review and calibration |
| Use at least 5 benchmarks per evaluation | Provides statistically meaningful results |

## Validation Cadence

| Frequency | Activity |
|---|---|
| Per new capability | Run benchmarks for that capability |
| Per quarter | Run a subset of benchmarks to detect regression |
| Per model change | Compare results when switching AI models |
| Per framework update | Validate that changes improve or maintain scores |