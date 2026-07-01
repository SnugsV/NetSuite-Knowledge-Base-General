# Benchmark Template

## Purpose

Standardized template for defining a validation benchmark. Every benchmark measures a specific capability (saved search, troubleshooting, workflow design, etc.).

## Template

```
BENCHMARK-[ID]: [Descriptive Title]

## Category

(Saved Search / SuiteScript / Workflow / Reporting / Troubleshooting / Configuration / Integration)

## Difficulty

(Beginner / Intermediate / Advanced)

## Business Scenario

[Description of the business situation — who, what, why]

## Task

What the AI must do:
1. [Step 1]
2. [Step 2]
3. [Step 3]

## Expected Reasoning Path

1. Classify the request as [category]
2. Route to [framework layer]
3. Open [specific framework documents]
4. Follow [specific skill or methodology]
5. Validate against [criteria]

## Required Metadata

What the AI must request or verify:
- [Item 1] — why it matters
- [Item 2] — why it matters

## Expected Questions

What the AI should ask the customer:
1. [Question 1] — why
2. [Question 2] — why

## Expected Routing

Framework layers in order:

1. Layer [X] — [reason]
2. Layer [X] — [reason]
3. Layer [X] — [reason]

## Expected Confidence

(Diagnosis confidence / Solution confidence)

## Acceptable Solutions

1. [Primary solution]
2. [Alternative solution, if applicable]

## Escalation Conditions

[When should the AI escalate? When should it resolve independently?]

## Evaluation Criteria

| Criterion | Weight | Score (1-10) |
|---|---|---|
| Business understanding | % | |
| Evidence gathered | % | |
| Reasoning quality | % | |
| Solution correctness | % | |
| Explanation quality | % | |
| Confidence accuracy | % | |
| Escalation decision | % | |

## Gold Standard Reference

[Link to Gold Standard file]
```

## Example: Filled Benchmark

```
BENCHMARK-SS-001: Inventory Below Reorder Point

## Category

Saved Search

## Difficulty

Beginner

## Business Scenario

An inventory manager needs to see a list of all items where the current on-hand quantity is below the reorder point. They want this emailed every morning.

## Task

1. Determine if a Saved Search is the appropriate tool
2. Gather the required metadata
3. Design the search criteria and results
4. Configure the email schedule
5. Validate the results

## Expected Reasoning Path

1. Classify: Reporting, recurring
2. Route to Solution Architect → Confirm saved search is appropriate
3. Route to Saved Search Metadata → Collect record type, field IDs, role
4. Route to Saved Search Builder Skill → Follow 11-step process

## Required Metadata

- Record type: Item
- Fields: On Hand, Reorder Point, Preferred Stock Level
- User role: Inventory Manager

## Expected Routing

Layer 5 (Solution Architect) → Layer 6 (Metadata) → Layer 4 (Skill)

## Expected Confidence

High — standard saved search with clear criteria

## Acceptable Solutions

Primary: Saved Search with criteria "On Hand is less than Reorder Point"
Alternative: Add Preferred Stock Level to results for context

## Escalation Conditions

No escalation needed for this standard search.

## Evaluation Criteria

| Criterion | Weight |
|---|---|
| Business understanding | 15% |
| Evidence gathered | 15% |
| Reasoning quality | 20% |
| Solution correctness | 30% |
| Explanation quality | 10% |
| Confidence accuracy | 5% |
| Escalation decision | 5% |
```