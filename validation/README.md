# AI Validation & Benchmark Framework

## Purpose

Prove that the platform consistently produces consultant-quality solutions. Every future capability must pass this validation framework before it is considered production-ready.

## Framework Documents

| Document | Purpose |
|---|---|
| [Validation Methodology](validation-methodology.md) | How benchmarks are executed, evaluated, and scored |
| [Consultant Scorecard](consultant-scorecard.md) | 8-dimension scorecard for evaluating consultant behavior |
| [Benchmark Template](benchmark-template.md) | Standardized benchmark definition template |
| [Gold Standard Template](gold-standard-template.md) | Expert-level solution definition template |
| [Benchmark Catalog](benchmark-catalog.md) | Master catalog of all validation benchmarks (30+ scenarios) |
| [Future Model Comparison](future-model-comparison.md) | Methodology for comparing AI models using identical benchmarks |
| [Acceptance Criteria](acceptance-criteria.md) | Minimum quality thresholds for every capability |

## Validation Philosophy

Validate consulting quality, not syntax.

Every benchmark evaluates:

- **Business Understanding** — Did the AI understand the objective before solving?
- **Evidence Gathering** — Did the AI collect enough evidence?
- **Reasoning** — Did the AI follow logical diagnostic steps?
- **NetSuite Knowledge** — Did the AI select the correct capability?
- **Solution Quality** — Is the solution technically and operationally sound?
- **Explanation** — Did the AI teach the customer?
- **Confidence** — Was confidence appropriately calibrated?
- **Escalation** — Did the AI escalate correctly?

## The Validation Process

```
Select benchmark → Run AI scenario → Record transcript →
Score (Consultant Scorecard) → Compare to Gold Standard →
Identify gaps → Report score → Recommend improvements
```

## What This Framework Enables

| Capability | How |
|---|---|
| **Certify AI consultants** | Pass a set of benchmarks with 85+ score |
| **Compare AI models** | Run identical benchmarks across models |
| **Detect regression** | Re-run benchmarks after framework updates |
| **Validate new capabilities** | Every new skill must pass relevant benchmarks |
| **Improve the platform** | Failed benchmarks reveal framework gaps |

## Acceptance Criteria

Every new capability must:

- Score 85+ / 100 on relevant benchmarks
- Pass 80% of benchmarks for that capability
- Align with the Gold Standard solution
- Include its own benchmarks and gold standards

## Related Documents

- [PLATFORM_ARCHITECTURE.md](../PLATFORM_ARCHITECTURE.md)
- [Agent Runtime](../knowledge-engine/AGENT_RUNTIME.md)
- [Experience Intelligence](../knowledge-engine/experience-intelligence/README.md)
- [All ERP learning paths](../docs/README.md)