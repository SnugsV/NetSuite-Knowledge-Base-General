# Execution Patterns

## Purpose

Standardized interaction patterns showing how the runtime adapts to different customer inputs.

## Pattern 1: Direct Question

**Customer says**: "What is a Bill of Materials?"
**Classification**: Question
**Runtime route**: Layer 1 (ERP Curriculum)
**Open**: `docs/manufacturing/bills-of-materials.md`
**Response**: Summary of what a BOM is, why it exists, business examples, cross-links to related topics.

## Pattern 2: Troubleshooting with Error Message

**Customer says**: "I'm getting error AV1005 when I try to ship."
**Classification**: Troubleshooting
**Runtime route**: Layer 3 (Context) → Layer 6 (Metadata) → Layer 4 (Skill) → Layer 2 (Support)
**Open**: 
- `knowledge-engine/customer-context/pacejet-context.md`
- `knowledge-engine/customer-metadata/pacejet-metadata.md`
- `knowledge-engine/ai-skills/pacejet-label-troubleshooter.md`
- `knowledge-engine/support-intelligence/pacejet-support.md`
**Response**: Error code explanation, root cause, resolution, escalation guidance.

## Pattern 3: Troubleshooting without Error Message

**Customer says**: "The tracking numbers aren't coming back to NetSuite."
**Classification**: Troubleshooting
**Runtime route**: Layer 6 (Metadata) → Layer 2 (Support)
**Open**:
- `knowledge-engine/customer-metadata/pacejet-metadata.md`
- `knowledge-engine/support-intelligence/pacejet-support.md`
**Response**: Diagnostic flow: check Pacejet portal → check API log → check script log → verify ASD fields. Confidence assessment.

## Pattern 4: Saved Search Request

**Customer says**: "I need a search that shows all customers who haven't ordered in 6 months."
**Classification**: Saved Search
**Runtime route**: Layer 5 (Solution Architect) → Layer 6 (Metadata) → Layer 4 (Skill)
**Open**:
- `knowledge-engine/solution-architect/solution-selection-trees.md`
- `knowledge-engine/customer-metadata/saved-search-metadata.md`
- `knowledge-engine/ai-skills/saved-search-builder.md`
**Response**: Follow 11-step skill: confirm appropriateness → gather context → select record type → design criteria → design results → document. Confidence assessment.

## Pattern 5: SuiteScript Request

**Customer says**: "We need a script that automatically updates the ship date when a fulfillment is created."
**Classification**: SuiteScript
**Runtime route**: Layer 5 (Solution Architect) → Layer 3 (Context) → Layer 6 (Metadata)
**Open**:
- `knowledge-engine/solution-architect/solution-selection-trees.md` (check automation section)
- `knowledge-engine/customer-context/customizations.md`
- `knowledge-engine/customer-metadata/scripting-metadata.md`
**Response**: First evaluate if workflow can do this. If not, provide script design (not production code). Recommend developer implement.

## Pattern 6: Configuration Request

**Customer says**: "We need to add FedEx as a carrier in Pacejet."
**Classification**: Configuration
**Runtime route**: Layer 5 (Solution Architect) → Layer 3 (Context) → Layer 2 (Support)
**Open**:
- `knowledge-engine/solution-architect/solution-selection-trees.md`
- `knowledge-engine/customer-context/pacejet-context.md`
- `knowledge-engine/support-intelligence/pacejet-support.md`
**Response**: Configuration steps, carrier activation process, test with single shipment, verify rates and labels.

## Pattern 7: CSV Upload

**Customer provides**: CSV file of transactions
**Classification**: Question or Troubleshooting (based on context)
**Runtime route**: Analyze CSV as evidence → Route to appropriate layer
**Response**: Use the CSV for analysis only. Do not import. Explain what the data shows and why it matters for the customer's situation.

## Pattern 8: Screenshot

**Customer provides**: Screenshot of an error or configuration page
**Classification**: Question or Troubleshooting
**Runtime route**: Analyze screenshot → Route to appropriate layer
**Response**: Interpret what the screenshot shows. Confirm understanding with the customer. Do not assume the full configuration based on a partial screenshot.

## Pattern 9: Training Request

**Customer says**: "Can you walk me through how to run a physical inventory?"
**Classification**: Training
**Runtime route**: Layer 1 (ERP Curriculum)
**Open**: 
- `docs/inventory/physical-inventory.md`
**Response**: Structured walkthrough with prerequisites, step-by-step process, common mistakes, and best practices.

## Pattern 10: Vague or Unclear Request

**Customer says**: "Inventory is wrong."
**Classification**: Troubleshooting (but needs clarification)
**Runtime route**: Layer 3 (Context) first
**Open**: `knowledge-engine/customer-context/customizations.md` (for general context)
**Response**: Clarifying questions before any diagnosis. "Which item? What quantity does the system show vs. what do you expect? Which location?" Do not attempt diagnosis without more information. Confidence: Unknown until clarified.

## Response Format for Every Pattern

Every response should include:

```
1. Summary — What the customer asked and what was found
2. Investigation — What was checked and what evidence was gathered
3. Recommendation — What to do (or why more information is needed)
4. Confidence — High/Medium/Low/Unknown with explanation
5. Next actions — What the customer should do next
```