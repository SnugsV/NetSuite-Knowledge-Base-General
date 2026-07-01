# Solution Architect Reasoning

## Purpose

Defines the core reasoning process for selecting the correct NetSuite capability. This methodology ensures the AI understands the business problem before choosing a solution.

## The Six-Phase Decision Process

### Phase 1: Understand the Business Objective

Before any solution is selected, confirm the business objective.

| Question | Purpose |
|---|---|
| "What business problem are you trying to solve?" | Defines the requirement |
| "What outcome would indicate success?" | Defines acceptance criteria |
| "Who will use this solution?" | Defines audience |
| "How often will it be used?" | Defines frequency — one-time, daily, real-time |
| "What is the budget for this solution?" | Defines resource constraints |

### Phase 2: Classify the Requirement

Classify the requirement into one of these categories:

| Category | Description | Example |
|---|---|---|
| **Informational** | The user needs to see data | Dashboard, report, search |
| **Transactional** | The user needs to create or modify data | Sales order, purchase order, journal entry |
| **Automation** | A process should happen automatically | Approval routing, email alert, data sync |
| **Integration** | NetSuite needs to exchange data with another system | E-commerce, bank, shipping |
| **Configuration** | A setting needs to be changed | Feature enablement, preference update |
| **Customization** | Standard functionality needs to be extended | Custom field, custom record, custom script |

### Phase 3: Navigate the Solution Selection Tree

Follow the solution selection tree for the classified requirement.

- **Informational** → [Selection Trees](solution-selection-trees.md#informational-requirements)
- **Transactional** → [Selection Trees](solution-selection-trees.md#transactional-requirements)
- **Automation** → [Selection Trees](solution-selection-trees.md#automation-requirements)
- **Integration** → [Selection Trees](solution-selection-trees.md#integration-requirements)
- **Configuration** → [Selection Trees](solution-selection-trees.md#configuration-requirements)
- **Customization** → [Selection Trees](solution-selection-trees.md#customization-requirements)

### Phase 4: Evaluate the Recommended Capability

Before finalizing, evaluate the recommended capability against: [Capability Reference](capability-reference.md)

- Does the capability exist in the customer's account? (Feature must be enabled)
- Does the customer have the required permissions?
- Does the capability meet the success criteria?
- What are the trade-offs?
- What is the ongoing maintenance cost?

### Phase 5: Consider Alternatives

Ask: "Is there another way to solve this problem?"

| If Default Is... | Consider... |
|---|---|
| Saved Search | SuiteAnalytics Workbook |
| Workflow | SuiteScript |
| Custom Field | Custom Segment |
| CSV Import | RESTlet or SuiteTalk |
| Standard Feature | SuiteApp or Bundle |

### Phase 6: Route to the Correct AI Skill

Once a capability is selected, route to the appropriate execution skill:

[Routing to AI Skills](routing-to-skills.md)

## The "Right Tool" Check

Before finalizing, verify:

- [ ] Does this capability solve the stated business problem?
- [ ] Does the customer already have this capability?
- [ ] Is this the simplest option that meets the requirement?
- [ ] What is the maintenance burden?
- [ ] What happens when the business requirement changes?

## Related Documents

- [Solution Selection Trees](solution-selection-trees.md)
- [Capability Reference](capability-reference.md)
- [Customer Context](../customer-context/README.md)