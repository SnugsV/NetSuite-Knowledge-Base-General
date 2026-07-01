# AI Solution Architect

This framework teaches an AI how to choose the correct NetSuite capability for a customer's business problem before executing any AI Skill. It is the architectural decision-making layer that sits above the AI Skills.

## Purpose

An experienced NetSuite consultant does not jump to solutions. They first understand the business objective, then evaluate which capability best fits the requirement — configuration, reporting, automation, or development. This framework codifies that process.

## The Architecture Decision Flow

```
Business Problem
       ↓
   Step 1: Understand the business objective
       ↓
   Step 2: Classify the requirement
       ↓
   Step 3: Navigate the Solution Selection Tree
       ↓
   Step 4: Evaluate the recommended capability
       ↓
   Step 5: Consider alternatives
       ↓
   Step 6: Route to the correct AI Skill
       ↓
  Execute
```

## Framework Documents

| Document | Purpose |
|---|---|
| [Solution Architect Reasoning](SOLUTION_ARCHITECT_REASONING.md) | Core decision-making methodology |
| [Solution Selection Trees](solution-selection-trees.md) | Structured decision trees from business problem to capability |
| [Capability Reference](capability-reference.md) | Detailed evaluation of each NetSuite capability |
| [Routing to AI Skills](routing-to-skills.md) | How to route from capability selection to execution |

## Related Documents

- [AI Skills](../ai-skills/README.md) — executable skills for each capability
- [Support Intelligence](../support-intelligence/README.md)
- [Customer Context](../customer-context/README.md)
- All ERP learning paths