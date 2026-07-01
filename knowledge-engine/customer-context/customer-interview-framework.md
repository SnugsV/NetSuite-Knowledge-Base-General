# Customer Interview Framework

## Purpose

A structured troubleshooting conversation ensures the AI does not miss critical information. This framework provides a repeatable process for every support interaction, while remaining flexible enough to adapt to different customer types.

## The Interview Structure

### Step 1: Establish the Baseline

Ask the following in order, not all at once:

| Question | Purpose |
|---|---|
| "What were you trying to accomplish?" | Understands the business objective |
| "What did you expect to happen?" | Understands the expected outcome |
| "What actually happened?" | Understands the actual outcome |
| "When did this start?" | Identifies when the issue began |
| "Has this ever worked correctly?" | Determines if it is a new or existing process |

### Step 2: Understand the Scope

| Question | Purpose |
|---|---|
| "Is this affecting one transaction or all transactions?" | Determines scope — single record vs. systemic |
| "Is this affecting one user or all users?" | Determines if it is user-specific |
| "Is this affecting one item or all items?" | Determines if it is item-specific |
| "Does it happen every time or intermittently?" | Determines frequency |

### Step 3: Gather Environmental Context

| Question | Purpose |
|---|---|
| "Were there any recent changes?" | Identifies configuration or customization changes |
| "Have you tried this in a sandbox?" | Determines if the issue can be reproduced |
| "Can you provide a screenshot?" | Confirms what the user is seeing |
| "What is the error message?" | Provides technical detail |
| "What is the transaction number?" | Enables record inspection |

### Step 4: Assess Impact

| Question | Purpose |
|---|---|
| "Is this blocking a critical business process?" | Determines urgency |
| "How many transactions are affected?" | Determines scale |
| "When does this need to be resolved by?" | Determines timeframe |
| "Who else is affected?" | Determines business impact |

## Adapting to Customer Type

### Administrator

- More technical, has configuration access
- Can verify features, permissions, and settings
- Can provide screenshots and error logs
- Prefer: "Can you check configuration for me? Navigate to..."

### Power User

- Knows their daily processes
- May not know configuration or customization details
- Cannot verify settings or permissions
- Prefer: "Can you describe exactly what steps you took?"

### Manager

- Focused on business impact, not technical details
- May not know the transaction-level specifics
- Prefer: "What is the business impact of this issue?"

### Consultant

- Technical, understands NetSuite concepts
- Has sandbox access
- Can test and verify independently
- Prefer: "Can you reproduce this in your sandbox?"

## Conversation Flow

```
Open:
  "Tell me what happened."

Clarify:
  "When did you first notice this?"
  "Has it worked before?"
  "Is it affecting everyone or just one user?"

Technical:
  "What transaction is affected?"
  "What error message do you see?"
  "Can you send a screenshot?"

Scope:
  "Does this happen with other items/transactions?"
  "Can you reproduce it?"

Impact:
  "How urgent is this?"
  "Is there a workaround?"
  "When do you need this resolved?"

Close:
  "I'm going to investigate and come back to you."
  "In the meantime, if you find anything else, please let me know."
```

## What Not to Do

- Do not ask every question at once — it overwhelms the customer
- Do not assume — ask for confirmation
- Do not skip the baseline — understand the expected behavior before diagnosing
- Do not ask for information you already have — it wastes the customer's time
- Do not ask the customer to do something they cannot do (e.g., a manager checking script deployments)

## Related Documents

- [Problem Classification](problem-classification.md)
- [Metadata Collection](metadata-collection.md)
- [Solution Confidence](solution-confidence.md)

## Oracle References

- [Oracle NetSuite Help Center: Support](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)