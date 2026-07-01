# Gold Standard Template

## Purpose

Defines the expert-level solution for a benchmark. The gold standard establishes what a consultant-quality response looks like, enabling objective comparison.

## Template

```
GOLD-[BENCHMARK-ID]: [Descriptive Title]

## Business Scenario

[Same as benchmark]

## Optimal Reasoning Path

1. [Step 1 — why this is the optimal first step]
2. [Step 2 — why this is the optimal second step]
3. [Step 3 — why this is the optimal third step]

## Reasoning

Why the gold standard path is the optimal approach:
- [Reason 1]
- [Reason 2]

## Complete Solution

[Full solution as an expert consultant would deliver it.
Include:
- Investigation performed
- Evidence gathered
- Reasoning
- Recommendation
- Explanation to the customer
- Validation steps
- Alternatives considered]

## Expected Questions

Context: [If applicable]
1. [Question] — [Why optimal]
2. [Question] — [Why optimal]

## Expected Metadata

1. [Metadata item] — [Why required]
2. [Metadata item] — [Why required]

## Acceptable Variations

[What deviations from the gold standard are still acceptable]

## Non-Acceptable Approaches

[What approaches would fail validation]

## Consultant Score Target

90+ / 100
```

## Gold Standard Example

```
GOLD-SS-001: Inventory Below Reorder Point

## Optimal Reasoning Path

1. Confirm saved search is appropriate → Yes, this is a recurring informational need
2. Gather metadata → Record type: Item; Fields: On Hand, Reorder Point; Role: Inventory Manager
3. Design criteria → Criteria: On Hand is less than Reorder Point
4. Design results → Item, On Hand, Reorder Point, Preferred Stock Level, Location
5. Configure schedule → Email daily at 7 AM to inventory manager
6. Validate → Run search, verify counts match expectations

## Complete Solution

**Investigation**: Confirmed that a Saved Search is the right tool — recurring, informational, needs email delivery.

**Recommendation**: Create a Saved Search on the Item record type with:
- Criteria: On Hand is less than Reorder Point
- Results: Name, Location, On Hand, Reorder Point, Preferred Stock Level, Available, On Order
- Schedule: Daily email to inventory manager
- Sort: Location ascending, then Reorder Point ascending (most urgent first)

**Explanation**: This search alerts the inventory manager every morning to items that need reordering. The Location field helps identify which warehouse needs stock. The Preferred Stock Level indicates the target quantity. The On Order field shows if stock is already incoming.

**Validation**: Run the search and verify that a few known low-stock items appear. The result count should be manageable (typically 10-50 items depending on catalog size).

## Consultant Score Target
95/100
```