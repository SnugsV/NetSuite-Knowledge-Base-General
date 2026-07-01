# Future Model Comparison

## Purpose

Design the evaluation methodology so multiple AI models can be compared using identical benchmarks. Do not compare models now — only design the methodology.

## Comparison Methodology

### Step 1: Select Benchmarks

Choose a representative set of benchmarks that cover the full range of capabilities:

| Category | Benchmarks | Coverage |
|---|---|---|
| Saved Search | SS-001, SS-003, SS-007 | Basic to intermediate search design |
| Troubleshooting | TRBL-001, TRBL-005, TRBL-009 | Integration, purchasing, sales |
| Workflow | WF-001, WF-003 | Automation design |
| Reporting | RPT-001, RPT-004 | Dashboard and operational reporting |
| Configuration | CFG-001, CFG-003 | User setup, workflow config |

### Step 2: Standardize the Test Environment

Each model must:
- Receive the identical benchmark scenario (no additional hints)
- Have the same time limit (e.g., 30 minutes per benchmark)
- Have access to the same repository content (or be evaluated on repository knowledge separately)
- Be evaluated by the same evaluator using the same scorecard

### Step 3: Score Using the Consultant Scorecard

Each model receives a score per benchmark using the 8-dimension scorecard.

### Step 4: Generate a Model Profile

```
Model: [Model Name]
Date evaluated: [Date]

| Benchmark | Category | Score |
|---|---|---|
| SS-001 | Saved Search | /100 |
| TRBL-001 | Troubleshooting | /100 |
| WF-001 | Workflow | /100 |
| RPT-001 | Reporting | /100 |
| CFG-001 | Configuration | /100 |

Overall: /100

Strengths:
- [Dimension where the model consistently scores 8+]

Weaknesses:
- [Dimension where the model consistently scores below 6]

Best for:
- [Types of tasks this model handles well]

Notes:
- [Any observations about behavior, reasoning quality, or confidence calibration]
```

### Step 5: Compare Across Models

Create a comparison table:

| Dimension | Model A | Model B | Model C |
|---|---|---|---|
| Business Understanding | | | |
| Evidence Gathering | | | |
| Reasoning | | | |
| NetSuite Knowledge | | | |
| Solution Quality | | | |
| Explanation | | | |
| Confidence | | | |
| Escalation | | | |
| **Overall** | | | |

## What the Comparison Should Measure

- **Absolute quality**: Which model produces the best solutions?
- **Consistency**: Which model has the least score variance across benchmarks?
- **Specialization**: Which models excel at specific categories?
- **Confidence calibration**: Which model is best at knowing what it does not know?
- **Framework dependency**: How much does each model benefit from the repository's structured knowledge?

## What the Comparison Should Not Measure

- **Speed**: Response time is a model capability, not a consulting quality metric
- **Cost**: Token efficiency varies by model and does not reflect consulting quality
- **Model-specific features**: Tool use, function calling, and context windows are model capabilities, not consulting skills

## When to Compare

| Trigger | Reason |
|---|---|
| Evaluating a new model for the platform | Determine if the model meets minimum consultant quality |
| Upgrading to a new model version | Detect regression or improvement |
| Quarterly benchmark review | Track model performance trends |
| Published model performance data becomes available | Correlate external benchmarks with internal consultant scores |

## Framework Independence

The comparison should also measure how each model performs without the repository framework:

- Run a subset of benchmarks with the repository as the only knowledge source
- Run the same benchmarks with no repository access
- The difference indicates the value added by the repository's structured knowledge

## Related Documents

- [Benchmark Catalog](benchmark-catalog.md)
- [Consultant Scorecard](consultant-scorecard.md)
- [Validation Methodology](validation-methodology.md)
- [Acceptance Criteria](acceptance-criteria.md)