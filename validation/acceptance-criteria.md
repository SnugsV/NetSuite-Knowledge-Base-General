# Acceptance Criteria

## Purpose

Defines the minimum quality thresholds for every capability in the platform. No capability should be considered complete without meeting these criteria.

## Capability Acceptance Criteria

Every new capability added to the platform must meet these criteria before it is considered production-ready:

### 1. Consultant Score Threshold

| Requirement | Target |
|---|---|
| Minimum Consultant Score | 85 / 100 |
| Target Consultant Score | 90 / 100 |
| Minimum Pass Rate | 80% of benchmarks for this capability must pass |

A capability that scores below 70 on any benchmark requires framework improvements before acceptance.

### 2. Gold Standard Alignment

The AI's solution must align with the Gold Standard on:

| Criterion | Required |
|---|---|
| Correct capability selection | Yes |
| Appropriate metadata collected | Yes |
| Correct reasoning path (may differ in order) | Yes |
| Solution correctness | Yes |
| Alternative approaches considered | Recommended |
| Confidence appropriate | Yes |
| Escalation decision appropriate | Yes |

### 3. Framework Requirements

| Requirement | Must Exist |
|---|---|
| Benchmark(s) for the capability | Yes |
| Gold Standard solution(s) | Yes |
| Consultant Scorecard evaluation | Yes |
| Validation Report | Yes |

### 4. Documentation Requirements

| Requirement | Must Exist |
|---|---|
| Any new framework documents cross-linked | Yes |
| Benchmark catalog updated | Yes |
| Gold standard files created | Yes |

## Component Acceptance Criteria

### New AI Skill

| Criterion | Minimum Score |
|---|---|
| Consultant Scorecard — Reasoning | 7/10 |
| Consultant Scorecard — Solution Quality | 8/10 |
| Pass rate on related benchmarks | 80% |

### New Integration Pack

| Criterion | Minimum Score |
|---|---|
| Consultant Scorecard — Evidence Gathering | 8/10 |
| Consultant Scorecard — NetSuite Knowledge | 7/10 |
| Support Intelligence patterns cover > 80% of known issues | Yes |

### New ERP Module

| Criterion | Minimum Score |
|---|---|
| Consultant Scorecard — NetSuite Knowledge | 8/10 |
| Consultant Scorecard — Explanation | 7/10 |
| Configuration benchmarks pass rate | 80% |

### New Framework Layer

| Criterion | Minimum Score |
|---|---|
| Consultant Scorecard — Reasoning | 8/10 |
| All related benchmarks pass rate | 80% |

## Release Acceptance Criteria

Before any release is considered complete:

| Criterion | Required |
|---|---|
| All new capabilities pass acceptance criteria | Yes |
| No regression on existing benchmarks | Yes |
| Validation reports created for new capabilities | Yes |
| Consultant Scorecards filed | Yes |
| Gold standards aligned | Yes |

## Regression Rules

If a platform update decreases any existing benchmark score by more than 10 points:

1. The update is blocked
2. The root cause must be identified
3. The framework must be fixed
4. The benchmark must be re-run
5. The score must recover to within 5 points of the original

## Exceptions

Exceptions to acceptance criteria require:

- Written justification
- Review by a human evaluator
- A timeline for meeting the criteria
- Documented in the Experience Intelligence Framework