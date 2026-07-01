# NetSuite Knowledge Base General — Platform Architecture

## What This Repository Is

This repository is a multi-layer AI Knowledge Platform that teaches future AI agents how to be competent NetSuite ERP consultants, support engineers, and solution architects. It is not a traditional documentation library. It is a codified reasoning system.

## Why It Exists

Traditional NetSuite documentation answers "what." The Oracle help center tells you what a field does, what a transaction does, what a feature does. It does not teach an AI how to think about ERP.

This repository exists to teach the "why" and "how":

- **Why** does this process exist in an ERP?
- **How** do experienced consultants approach a troubleshooting session?
- **How** do solution architects choose between options?
- **How** should an AI gather context before offering a recommendation?

## The Six-Layer Architecture

### Layer 1: ERP Curriculum

**Location**: `docs/`

**Purpose**: Teaches ERP business processes — what things are, why they exist, how they connect.

**Modules**:

| Module | Status | Articles | What It Teaches |
|---|---|---|---|
| Getting Started | Complete | 13 | NetSuite fundamentals |
| Administration | Complete | 18 | Users, roles, permissions, setup |
| Saved Searches | Complete | 23 | Search-driven reporting |
| Inventory (3 phases) | Complete | 29 | Item records, operations, advanced |
| Purchasing | Complete | 12 | Procure-to-Pay lifecycle |
| Sales | Complete | 12 | Order-to-Cash lifecycle |
| Manufacturing | Complete | 14 | Plan-to-Produce lifecycle |
| Accounting | Complete | 16 | Record-to-Report lifecycle |

**Scope boundary**: Documents go in `docs/<module>/`. Each module is a complete learning path with module README, articles, glossary, and best practices. Do not create articles that belong in another module.

### Layer 2: Support Intelligence

**Location**: `knowledge-engine/support-intelligence/`

**Purpose**: Teaches an AI how to troubleshoot problems. Each domain document covers common questions, diagnostic patterns, conversation frameworks, root causes, and escalation criteria.

**Documents**: 8 ERP domain documents (purchasing, sales, inventory, manufacturing, accounting, administration, saved searches, integration) + 1 ecosystem integration document (Pacejet).

**Scope boundary**: Support documents go in `knowledge-engine/support-intelligence/<domain>-support.md`. Each document follows the structure defined in `REASONING_FRAMEWORK.md`.

### Layer 3: Customer Context

**Location**: `knowledge-engine/customer-context/`

**Purpose**: Teaches an AI how to understand a customer's unique environment before attempting a solution. Covers company profile, NetSuite configuration, customizations, metadata collection, problem classification, interviewing, confidence assessment, and escalation.

**Documents**: Core methodology + 9 domain context documents + 1 ecosystem integration context document (Pacejet).

**Scope boundary**: Context documents go in `knowledge-engine/customer-context/<domain>-context.md`. Each document defines required customer information and how missing information affects confidence.

### Layer 4: AI Skills

**Location**: `knowledge-engine/ai-skills/`

**Purpose**: Executable reasoning guides that teach an AI how to perform specific tasks — building saved searches, troubleshooting shipping labels, diagnosing rate issues. Each skill includes decision trees, step-by-step reasoning, validation checklists, and failure modes.

**Documents**: Saved Search Builder, Pacejet Rate Troubleshooter, Pacejet Label Troubleshooter.

**Scope boundary**: Skills go in `knowledge-engine/ai-skills/<descriptive-name>.md`. Each skill teaches reasoning, not templates.

### Layer 5: Solution Architect

**Location**: `knowledge-engine/solution-architect/`

**Purpose**: Architectural decision-making layer that teaches an AI how to choose the correct NetSuite capability for a business problem before executing any AI Skill. Covers requirement classification, solution selection trees, capability evaluation, and routing to AI Skills.

**Documents**: Core reasoning methodology, selection trees, capability reference, routing guide.

**Scope boundary**: Solution architecture documents go in `knowledge-engine/solution-architect/`. Updates to the capability reference should be made when new capabilities are documented.

### Layer 6: Customer Metadata

**Location**: `knowledge-engine/customer-metadata/`

**Purpose**: Defines exactly what customer-specific metadata must be collected before designing, troubleshooting, or generating any NetSuite solution. Prevents AI from making assumptions about a customer's environment.

**Documents**: Core methodology + 5 domain metadata documents + 1 ecosystem integration metadata document (Pacejet).

**Scope boundary**: Metadata documents go in `knowledge-engine/customer-metadata/<domain>-metadata.md`. Each document classifies metadata as required/optional/nice-to-have and defines confidence impact.

---

## How a Customer Question Flows Through the System

```
Customer: "Our shipping labels stopped working."

1. Layer 3 (Customer Context)
   → What is the customer's Pacejet version? NetSuite bundle version?
   → Which carriers are enabled? Any recent changes?

2. Layer 2 (Support Intelligence)
   → Open pacejet-support.md
   → Map to "Label won't generate" pattern
   → Follow diagnostic: check error → verify data → check carrier → check config

3. Layer 4 (AI Skills)
   → Open pacejet-label-troubleshooter.md
   → 7-step skill guides the investigation
   → Decision trees at each step

4. Layer 6 (Metadata)
   → Request API log, error log, sample shipment
   → Validate metadata completeness

5. Layer 1 (ERP Curriculum — if needed)
   → Reference: how Item Fulfillment works
   → Reference: how carrier setup works

6. Layer 5 (Solution Architect — for new requests)
   → Is this a configuration change, a bug, or a new requirement?
   → Should Pacejet handle this, or does it need custom SuiteScript?
```

---

## How Integration Intelligence Packs Fit

Ecosystem integrations (Pacejet, and future ones like Avalara, Celigo, Shopify, etc.) are the first practical validation of the six-layer architecture. Each integration pack spans all six layers:

| Layer | Integration Contribution |
|---|---|
| **Layer 1** | `docs/integrations/<name>/` — learning path |
| **Layer 2** | `knowledge-engine/support-intelligence/<name>-support.md` |
| **Layer 3** | `knowledge-engine/customer-context/<name>-context.md` |
| **Layer 4** | `knowledge-engine/ai-skills/<name>-*-skill.md` |
| **Layer 5** | Capability reference update |
| **Layer 6** | `knowledge-engine/customer-metadata/<name>-metadata.md` |

### Adding a New Integration

1. Create `docs/integrations/<name>/` with a learning path (at minimum: What Is X, Setup, Core Workflow)
2. Create the support intelligence document in Layer 2
3. Create the customer context document in Layer 3
4. Create AI skills for common troubleshooting scenarios in Layer 4
5. Update the Solution Architect capability reference in Layer 5
6. Create the metadata document in Layer 6

Follow the Pacejet structure as the reference template. The document organization, section headings, and reasoning patterns are designed to be copied and adapted.

---

## What Should Be Added

| Type | Goes In |
|---|---|
| ERP module learning path | `docs/<module>/` |
| Support intelligence for a domain | `knowledge-engine/support-intelligence/<name>-support.md` |
| Customer context for a domain | `knowledge-engine/customer-context/<name>-context.md` |
| Reusable task skill | `knowledge-engine/ai-skills/<name>.md` |
| Capability reference entry | `knowledge-engine/solution-architect/capability-reference.md` |
| Metadata requirements | `knowledge-engine/customer-metadata/<name>-metadata.md` |
| Integration intelligence pack | All six layers, under the integration name |
| Architecture decision record | `knowledge-engine/decisions/ADR-<number>-<title>.md` |

## What Should Not Be Added

| Type | Why Not |
|---|---|
| Oracle documentation copy | Oracle content is copyrighted. Reference it; do not reproduce it. |
| AI system prompts | Prompts change with model versions. Document reasoning, not prompts. |
| Personal credentials or tokens | Security. Use gh auth, not stored credentials. |
| Non-NetSuite ERP content | This platform is NetSuite-specific. General ERP concepts go in context, not here. |
| Unrelated content | The platform is focused on NetSuite ERP knowledge. |

---

## How Future AI Agents Should Use the Repository

**First time**: Read this file, then read `knowledge-engine/MASTER_PROJECT_PROMPT.md`.

**Before every task**:
1. `git pull origin main` — ensure latest content
2. Read `knowledge-engine/PROJECT_MEMORY.md` — startup sequence
3. Read `PROJECT_STATUS.md` and `SESSION_REPORT.md` — current state
4. Create a feature branch from `main`

**When solving a customer problem**:
1. Start with Layer 3 — gather customer context
2. Move to Layer 2 — classify the problem and follow support patterns
3. If a skill exists in Layer 4 — execute the skill
4. Use Layer 6 metadata documents to confirm what evidence is needed
5. Reference Layer 1 learning paths for deeper understanding
6. Use Layer 5 for architectural decisions

**When building new content**:
- Follow the established document structure for the layer you are contributing to
- Cross-link to related documents in other layers
- Do not modify framework core documents without an ADR

---

## PR #18 and PR #19 Situation

### Current State

- **PR #18** (`release/2.1-pacejet-planning`): Release plan for Pacejet integration architecture. Planning-only document: `RELEASE_PLAN_2.1.md`.
- **PR #19** (`release/2.1-pacejet-intelligence`): Complete implementation of the Pacejet Intelligence Pack across all six layers. 12 documents.

### Recommendation

**PR #19 fully supersedes PR #18.** The planning document in PR #18 was used as the blueprint for PR #19. All useful planning content was incorporated into the implementation.

**Recommended action**:
1. **Close PR #18** — the planning phase is complete and its output was consumed by PR #19
2. **Preserve `RELEASE_PLAN_2.1.md`** if it still contains useful planning context. Option: merge it into main as a standalone planning artifact, or note that its content is incorporated into PR #19's delivery.
3. **Focus review on PR #19** — the actual Pacejet implementation

---

## Repository Health

| Criterion | Score (1-10) |
|---|---|
| Structure | 9 — Six-layer architecture is clean and extensible |
| Governance | 8 — Framework documents are stable; extensions follow patterns |
| Content (ERP) | 8 — 8 complete ERP modules (~150 articles) |
| Content (AI) | 6 — 40+ framework documents across 5 extension layers |
| Extensibility | 9 — Pacejet validates the template; future integrations copy the structure |
| Automation | 2 — No CI/CD, no automated validation, no MkDocs |
| PR Hygiene | 4 — 16 open PRs. Needs triage and merging. |

**Critical issue**: 16 of 19 PRs remain open. The platform cannot be considered "live" until the framework extensions (PRs #13-#17) are merged and the ERP modules (PRs #4-#12) are reviewed and merged.

## Related Documents

- [knowledge-engine/MASTER_PROJECT_PROMPT.md](knowledge-engine/MASTER_PROJECT_PROMPT.md)
- [knowledge-engine/README.md](knowledge-engine/README.md)
- [PROJECT_STATUS.md](PROJECT_STATUS.md)
- [BACKLOG.md](BACKLOG.md)
- [RELEASE_PLAN_2.1.md](RELEASE_PLAN_2.1.md) (PR #18 planning artifact)

## Oracle References

- [Oracle NetSuite Help Center](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Pacejet Knowledge Base](https://pacejet.help.descartesservices.com/)