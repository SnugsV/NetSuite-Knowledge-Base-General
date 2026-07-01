# Agent Runtime Framework

## Purpose

This document defines the standard operating procedure for every AI agent that consumes this repository. It describes how an agent should process a customer request from beginning to end — ensuring consistent, explainable, evidence-based reasoning regardless of the NetSuite module or integration involved.

## Scope

This framework is platform-agnostic. It works with Hermes, ChatGPT, Claude, OpenAI Agents, MCP servers, or any future enterprise AI platform. It does not assume a specific model.

---

## The AI Execution Lifecycle

Every request follows this 10-step sequence:

```
1. Understand Business Objective
         ↓
2. Classify the Request
         ↓
3. Invoke the Solution Architect
         ↓
4. Gather Customer Context
         ↓
5. Validate Customer Metadata
         ↓
6. Invoke the Appropriate AI Skill
         ↓
7. Apply Support Intelligence
         ↓
8. Validate the Proposed Solution
         ↓
9. Explain the Recommendation
         ↓
10. Recommend Next Actions
```

---

### Step 1: Understand the Business Objective

Before any solution is selected, confirm the business objective.

| Question | Purpose |
|---|---|
| "What business problem are you trying to solve?" | Defines the requirement |
| "What outcome would indicate success?" | Defines acceptance criteria |
| "Who will use this solution?" | Defines audience |
| "How often will it be used?" | Defines frequency |
| "What is the budget or effort available?" | Defines constraints |

**Failure mode to avoid**: Jumping to a solution before understanding the problem.

**Mitigation**: Do not proceed to Step 2 until the business objective is captured in one sentence.

### Step 2: Classify the Request

Classify the request into one of these categories. The classification determines which path the runtime follows.

| Category | Description | Next Action |
|---|---|---|
| **Question** | The user wants to understand something | Answer directly using Layer 1 (ERP Curriculum) |
| **Troubleshooting** | Something is broken or not working | Route to Layer 2 (Support Intelligence) |
| **Configuration** | A setting needs to be changed | Route to Layer 5 (Solution Architect) |
| **Reporting** | The user needs to see data | Route to Layer 4 (AI Skills — Saved Search Builder) |
| **Saved Search** | The user needs a specific search | Route to Layer 4 (Saved Search Builder Skill) |
| **Workflow** | Automation is needed | Route to Layer 5 (Solution Architect) |
| **SuiteScript** | Custom code is needed | Route to Layer 6 (Metadata) then Layer 4 |
| **Integration** | Data sync or connector issue | Route to Layer 3 (Customer Context) then Layer 2 |
| **Training** | User needs to learn how to do something | Route to Layer 1 (ERP Curriculum) |
| **Optimization** | An existing process needs improvement | Route to Layer 1 + Layer 5 |

### Step 3: Invoke the Solution Architect

Before attempting a solution, determine the most appropriate NetSuite capability.

**Open**: `knowledge-engine/solution-architect/SOLUTION_ARCHITECT_REASONING.md`

Follow the 6-phase decision process:

1. Understand the business objective (already done in Step 1)
2. Classify the requirement (already done in Step 2)
3. Navigate the solution selection trees
4. Evaluate the recommended capability against the capability reference
5. Consider alternatives
6. Route to the correct AI Skill

**Confidence check**: If the recommended capability does not exist in the customer's account (feature not enabled), note this. Do not assume the feature exists without verification.

### Step 4: Gather Customer Context

Open the appropriate customer context document:

- `knowledge-engine/customer-context/<domain>-context.md`
- For integrations: use the integration-specific context document

Collect the information listed under "Required Information." If any required information is unavailable:

- **Note the gap** — do not guess
- **Explain why it matters** — "This is needed because [reason]"
- **Request it from the customer** — "Could you check [specific location] for [specific information]?"

**Failure mode to avoid**: Assuming the customer's configuration matches a default setup.

**Mitigation**: Always check at least: enabled features, existing customizations, user permissions, installed bundles.

### Step 5: Validate Customer Metadata

Open the appropriate metadata document:

- `knowledge-engine/customer-metadata/<domain>-metadata.md`

Check each required metadata item. Score confidence:

| Scenario | Confidence | Action |
|---|---|---|
| All required metadata collected | High | Proceed to step 6 |
| Some required metadata missing | Medium | Proceed, note the gaps |
| Most required metadata missing | Low | Do not proceed — request metadata first |
| No metadata collected | Unknown | Do not proceed — request metadata first |

**Failure mode to avoid**: Proceeding with insufficient evidence.

**Mitigation**: If confidence is Low or Unknown, explain what metadata is needed, why it matters, and how to collect it. Do not guess.

### Step 6: Invoke the Appropriate AI Skill

If an AI Skill exists for the task, open and follow it:

- `knowledge-engine/ai-skills/saved-search-builder.md`
- `knowledge-engine/ai-skills/pacejet-rate-troubleshooter.md`
- `knowledge-engine/ai-skills/pacejet-label-troubleshooter.md`

If no skill exists, use the Solution Architect's capability reference as guidance and document the execution steps manually.

**Failure mode to avoid**: Creating a solution from scratch when a skill exists.

**Mitigation**: Check the ai-skills directory before building any solution from scratch.

### Step 7: Apply Support Intelligence

After executing the skill, compare the proposed solution against known troubleshooting patterns:

- `knowledge-engine/support-intelligence/<domain>-support.md`

Check for:
- Common edge cases that the skill did not address
- Known failure modes of this approach
- Escalation criteria that may apply

**Failure mode to avoid**: Delivering a solution that has known failure modes.

**Mitigation**: Before finalizing, check the support intelligence document for "Common Mistakes" and "Failure Modes."

### Step 8: Validate the Proposed Solution

Check the proposed solution against these criteria:

| Criterion | Check |
|---|---|
| **Business reasoning** | Does the solution solve the stated business problem? |
| **Technical accuracy** | Is the solution technically correct for the customer's configuration? |
| **Confidence level** | Is the confidence level appropriate for this recommendation? |
| **Alternative approaches** | Have alternative approaches been considered? |
| **Edge cases** | Have known failure modes been addressed? |
| **Audience** | Can the person implementing this solution follow the instructions? |

### Step 9: Explain the Recommendation

Structure the explanation to teach, not simply answer.

```
**Summary**: One sentence describing what was found and what is recommended.

**Problem**: What the customer reported.

**Investigation**: What was checked and what was found.
- Evidence gathered
- Records inspected
- Patterns matched

**Root cause**: What is causing the issue (or why the configuration is appropriate).

**Recommended solution**: What to do.
1. Step one
2. Step two
3. Step three

**Alternative approaches**: If the recommended solution does not work, try these.

**Next actions**: What the customer should do after applying the solution.
```

### Step 10: Recommend Next Actions

After delivering the recommendation, suggest what the customer should do next:

| Situation | Recommended Next Action |
|---|---|
| Solution can be tested | "Test this in your sandbox first." |
| Configuration change needed | "An administrator will need to make this change." |
| SuiteScript change needed | "A developer should review and implement this." |
| Integration change needed | "Contact your integration vendor to verify this configuration." |
| Issue may be a known product behavior | "Review the release notes or contact Oracle Support." |
| Issue requires Pacejet support | "Open a case with Pacejet support with these details." |

---

## Confidence Framework

### Confidence Levels

| Level | Definition | Action |
|---|---|---|
| **High** | Root cause clear, fix known, environment matches expectations, evidence complete | Recommend with confidence. Include verification steps. |
| **Medium** | Likely cause, standard fix, but some evidence missing or environment uncertain | Recommend with caveats. Explain what is uncertain. |
| **Low** | Multiple possible causes, insufficient evidence, environment unknown | Request more information before recommending. |
| **Unknown** | No evidence, no known pattern, environment completely unknown | Do not recommend. Gather context first. |

### Confidence Degradation Factors

Confidence should be downgraded when:

| Factor | Downgrade | Why |
|---|---|---|
| Customer has significant customizations | High → Medium | Customizations may override standard behavior |
| Customer configuration not confirmed | Medium → Low | Assumptions may be wrong |
| Issue is intermittent | Medium → Low | Intermittent issues are harder to diagnose |
| Cannot reproduce in sandbox | Medium → Low | Cannot verify the fix |
| Multiple modules involved | High → Medium | Cross-module issues may have multiple causes |
| Vendor behavior undocumented | High → Medium | Cannot confirm expected behavior |

---

## Failure Modes

| Failure Mode | Description | Mitigation |
|---|---|---|
| **Jumping to conclusions** | Recommending a solution before understanding the problem | Complete Step 1 (Business Objective) before any solution discussion |
| **Assuming configuration** | Guessing that a feature is enabled or disabled | Always verify in Step 4 (Customer Context) |
| **Ignoring customizations** | Forgetting that scripts, workflows, or custom fields may affect behavior | Check customizations in Step 4 |
| **Skipping metadata validation** | Proceeding without evidence | Complete Step 5 — if confidence < Medium, do not proceed |
| **Overusing SuiteScript** | Recommending custom code when configuration or workflow would work | Use Solution Architect (Step 3) to rule out simpler options first |
| **Ignoring native functionality** | Recommending a solution that already exists in NetSuite | Check standard features before recommending customization |
| **Incorrect prioritization** | Solving the wrong problem | Confirm the business objective in Step 1 |
| **Missing escalation** | Spending too long on a problem that needs human expertise | Use escalation criteria defined in each support document |
| **Oversimplification** | Providing a partial solution that does not address all requirements | Validate against all criteria in Step 8 |

---

## Interaction Patterns

### Pattern 1: Customer Asks a Question

```
Customer: "What is the difference between a Saved Search and a Report?"

Runtime flow:
1. Classify: Question
2. Route to Layer 1 (ERP Curriculum)
3. Reference: docs/saved-searches/saved-search-vs-reports.md
4. Answer directly
5. Suggest follow-up: Next topic they should learn
```

### Pattern 2: Customer Reports an Error

```
Customer: "The label won't generate in Pacejet."

Runtime flow:
1. Classify: Troubleshooting
2. Route to Layer 3 (Customer Context): pacejet-context.md
3. Route to Layer 6 (Metadata): pacejet-metadata.md
4. Request: Error message, shipment data, version
5. Route to Layer 4 (AI Skill): pacejet-label-troubleshooter.md
6. Follow 7-step diagnostic process
7. Route to Layer 2 (Support Intelligence): pacejet-support.md
8. Validate against known patterns
9. Explain the finding and resolution
10. Recommend next actions
```

### Pattern 3: Customer Requests a Configuration Change

```
Customer: "We need to add a new carrier in Pacejet."

Runtime flow:
1. Classify: Configuration
2. Route to Layer 3 (Customer Context): pacejet-context.md
3. Gather: Which carrier, contract details, service levels
4. Route to Layer 2: Check for known carrier configuration issues
5. Provide step-by-step configuration guidance
6. Recommend: Test with a single shipment before activating
```

### Pattern 4: Customer Requests a Saved Search

```
Customer: "I need a search that shows all open sales orders over $10,000."

Runtime flow:
1. Classify: Saved Search
2. Route to Layer 5 (Solution Architect): Confirm saved search is appropriate
3. Route to Layer 4 (AI Skill): saved-search-builder.md
4. Follow 11-step skill process
5. Route to Layer 6: Collect record type, field IDs, role
6. Build and document the search
7. Validate against expected results
8. Explain the design decisions
```

### Pattern 5: Customer Provides a CSV or Screenshot

```
Customer sends a CSV file.

Runtime flow:
1. Classify: Question or Troubleshooting (based on what they say)
2. Analyze the CSV as evidence
3. Do NOT import the CSV or make changes — use it as reference data
4. If the CSV shows data issues, route to appropriate support intelligence
5. Explain what the data shows and why it matters
```

### Pattern 6: Customer Requests Custom SuiteScript

```
Customer: "We need a script that does [custom behavior]."

Runtime flow:
1. Classify: SuiteScript
2. Route to Layer 5 (Solution Architect): Is configuration or workflow sufficient?
3. Evaluate: Can this be done with workflow instead?
4. If SuiteScript is genuinely required:
   a. Route to Layer 6: Collect metadata (existing scripts, governance limits)
   b. Route to Layer 3: Document customizations and scripts
5. Provide design for the script (not production code)
6. Recommend: A developer should implement and test this
```

---

## Runtime Decision Trees

### Main Dispatch Decision Tree

```
Customer request received.
  │
  ├── Is it a Question?
  │   └── Yes → Answer from Layer 1 (ERP Curriculum). Done.
  │
  ├── Is it Troubleshooting?
  │   └── Yes → Route through: Context → Metadata → Support Intelligence → Skill
  │
  ├── Is it Configuration or Reporting?
  │   └── Yes → Route through: Solution Architect → Metadata → Skill
  │
  ├── Is it a Saved Search?
  │   └── Yes → Route through: Solution Architect → Metadata → Saved Search Builder Skill
  │
  ├── Is it SuiteScript or Workflow?
  │   └── Yes → Route through: Solution Architect → Context → Metadata → Skill (if exists)
  │
  ├── Is it Integration?
  │   └── Yes → Route through: Context → Metadata → Support Intelligence → Escalate if needed
  │
  └── Is it Training or Optimization?
      └── Yes → Route through: Layer 1 + Layer 5
```

### When to Escalate

```
Confidence assessment from Step 5.
  │
  ├── Is confidence Low or Unknown?
  │   └── Yes → Request more information. Do not recommend.
  │
  ├── Is the root cause not found?
  │   └── Yes → Escalate. Provide what was tried and what metadata was gathered.
  │
  ├── Does the solution require admin access?
  │   └── Yes → Provide instructions. Recommend admin implement.
  │
  ├── Does the solution require SuiteScript changes?
  │   └── Yes → Provide design. Recommend developer implement.
  │
  ├── Does the issue involve a suspected bug?
  │   └── Yes → Recommend opening a case with Oracle or Pacejet support.
  │
  └── Otherwise → Recommend independently.
```

---

## Related Documents

- [PLATFORM_ARCHITECTURE.md](../PLATFORM_ARCHITECTURE.md)
- [knowledge-engine/MASTER_PROJECT_PROMPT.md](MASTER_PROJECT_PROMPT.md)
- [knowledge-engine/solution-architect/SOLUTION_ARCHITECT_REASONING.md](solution-architect/SOLUTION_ARCHITECT_REASONING.md)
- [knowledge-engine/OPERATING_PROCEDURE.md](OPERATING_PROCEDURE.md)
- [knowledge-engine/PROJECT_MEMORY.md](PROJECT_MEMORY.md)
- [runtime-decision-trees.md](runtime-decision-trees.md)
- [execution-patterns.md](execution-patterns.md)