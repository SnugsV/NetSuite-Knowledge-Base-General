# NetSuite Knowledge Base General — Platform Architecture

## What This Repository Is

This repository is a multi-layer AI Knowledge Platform that teaches AI agents how to be competent NetSuite ERP consultants, support engineers, and solution architects. It is not a traditional documentation library. It is a codified reasoning system.

## Why It Exists

Traditional NetSuite documentation answers "what." This repository teaches the "why" and "how" — why ERP processes exist, how experienced consultants troubleshoot, how solution architects choose between options, and how an AI should gather context before offering recommendations.

## The Six-Layer Architecture

### Layer 1: ERP Curriculum

**Location**: `docs/`

**Purpose**: Teaches ERP business processes.

| Module | Articles | Status |
|---|---|---|
| Getting Started | 13 | Complete |
| Administration | 18 | Complete |
| Saved Searches | 23 | Complete |
| Inventory (3 phases) | 29 | Complete |
| Purchasing | 12 | Complete |
| Sales | 12 | Complete |
| Manufacturing | 14 | Complete |
| Accounting | 16 | Complete |
| Integrations (Pacejet) | 6 | Complete |

**Scope**: Documents go in `docs/<module>/`. Each module is a complete learning path.

### Layer 2: Support Intelligence

**Location**: `knowledge-engine/support-intelligence/`

**Purpose**: Teaches an AI how to troubleshoot problems. Each document covers common questions, diagnostic patterns, root causes, and escalation criteria.

**Documents**: 8 ERP domain documents + 1 integration (Pacejet).

**Scope**: `knowledge-engine/support-intelligence/<domain>-support.md`

### Layer 3: Customer Context

**Location**: `knowledge-engine/customer-context/`

**Purpose**: Teaches an AI how to understand a customer's environment before attempting a solution.

**Documents**: Core methodology + 9 context documents + Pacejet context.

**Scope**: `knowledge-engine/customer-context/<domain>-context.md`

### Layer 4: AI Skills

**Location**: `knowledge-engine/ai-skills/`

**Purpose**: Executable reasoning guides for specific tasks — building saved searches, troubleshooting labels, diagnosing rates.

**Documents**: Saved Search Builder, Pacejet Rate Troubleshooter, Pacejet Label Troubleshooter.

**Scope**: `knowledge-engine/ai-skills/<descriptive-name>.md`

### Layer 5: Solution Architect

**Location**: `knowledge-engine/solution-architect/`

**Purpose**: Decision-making layer for choosing the correct capability before executing any skill.

**Documents**: Reasoning methodology, selection trees, capability reference, routing guide.

**Scope**: `knowledge-engine/solution-architect/`

### Layer 6: Customer Metadata

**Location**: `knowledge-engine/customer-metadata/`

**Purpose**: Defines what metadata must be collected before designing any solution. Prevents assumptions.

**Documents**: Core methodology + 5 domain metadata documents + Pacejet metadata.

**Scope**: `knowledge-engine/customer-metadata/<domain>-metadata.md`

## How a Customer Question Flows Through the System

```text
Customer: "Our shipping labels stopped working."

Layer 3 (Context) -> Version? Bundle? Carriers? Changes?
Layer 2 (Support) -> Open pacejet-support.md -> Diagnostic pattern
Layer 4 (Skills) -> Follow label-troubleshooter -> 7-step skill
Layer 6 (Metadata) -> API log, error log, sample shipment
Layer 1 (Curriculum) -> Reference: fulfillment, carrier setup
Layer 5 (Architect) -> Config change? Bug? New requirement?
```

## How Integration Packs Fit

Each integration spans all six layers using Pacejet as the template:

| Layer | Integration File |
|---|---|
| 1 | `docs/integrations/<name>/` |
| 2 | `knowledge-engine/support-intelligence/<name>-support.md` |
| 3 | `knowledge-engine/customer-context/<name>-context.md` |
| 4 | `knowledge-engine/ai-skills/<name>-*-skill.md` |
| 5 | Capability reference update |
| 6 | `knowledge-engine/customer-metadata/<name>-metadata.md` |

## What Belongs in the Platform

| Type | Location |
|---|---|
| ERP module learning path | `docs/<module>/` |
| Support intelligence | `knowledge-engine/support-intelligence/` |
| Customer context | `knowledge-engine/customer-context/` |
| AI skill | `knowledge-engine/ai-skills/` |
| Capability reference | `knowledge-engine/solution-architect/` |
| Metadata requirements | `knowledge-engine/customer-metadata/` |
| Integration pack | All six layers |
| ADR | `knowledge-engine/decisions/` |

## What Does Not Belong

- **Oracle documentation copy** — reference it, do not reproduce it
- **Private implementation details** — company-specific SOPs, screenshots, custom fields, saved searches, workflows, scripts, pricing, customer examples, credentials, and proprietary processes belong in private overlays or internal knowledge sources
- **AI system prompts** — prompts change with model versions
- **Credentials or tokens** — use authenticated tools, not stored credentials
- **Non-NetSuite ERP content** — keep focused on NetSuite
- **Unrelated content** — the platform is NetSuite ERP specific

## How AI Agents Should Use the Repository

Start with [AGENTS.md](AGENTS.md), then use the knowledge-engine documents for deeper framework guidance.

When solving a problem, start with customer context, move to support intelligence, execute the relevant AI skill, collect required metadata, reference the curriculum, and use the solution architect layer for capability decisions.

## Repository Health

Repository health should be tracked in the active project status and health files rather than hard-coded here. This avoids stale PR counts, outdated readiness claims, and duplicated status reporting.
