# Customer Context Discovery Methodology

## Purpose

Defines the core reasoning process for discovering customer context. This methodology ensures that the AI gathers systematic, relevant information before attempting a solution.

## The Discovery Phases

### Phase 1: Initial Triage

In the first interaction, determine:

- **Who is contacting you?** (Administrator, power user, consultant, manager)
- **What is their relationship to NetSuite?** (Daily user, configuration-level access, SuiteScript developer)
- **What is the stated problem?** (Capture their exact words — they may not describe the root cause)
- **How urgent is it?** (Production down, period close blocked, minor inconvenience)

### Phase 2: Problem Classification

Classify the problem into one or more categories:

- Configuration
- Permissions
- Customization
- Data integrity
- Accounting
- Inventory
- Manufacturing
- Performance
- Integration
- Workflow
- Script
- Reporting
- User training

Multiple categories may apply. A fulfillment issue could be inventory, permissions, and workflow simultaneously.

### Phase 3: Company Profile

Gather information about the company:

- Industry and business model
- Company size and transaction volume
- Whether they use OneWorld, manufacturing, WMS
- International operations and currencies
- Number of users and locations

### Phase 4: NetSuite Configuration

Discover the account configuration:

- Enabled features (start with the affected module)
- Bundles and SuiteApps installed
- Third-party integrations
- Customization level (custom records, fields, scripts)

### Phase 5: Metadata Collection

Request specific exports based on the problem:

- Saved Searches (standard and custom)
- Custom field definitions
- Script and workflow details
- Sample transactions
- Configuration screenshots
- Error logs

### Phase 6: Validation

Before finalizing any recommendation:

- Does the recommended solution align with their configuration?
- Have you verified against a similar scenario?
- Can the customer reproduce the issue in a sandbox?
- Is there sufficient evidence to support the diagnosis?

### Phase 7: Confidence Assessment

- **High confidence**: Clear cause, known fix, verified in a similar environment
- **Medium confidence**: Likely cause, standard fix, but environment is different
- **Low confidence**: Possible causes, requires additional information
- **Unknown**: Cannot determine with available information

## The "Enough Information" Check

Before offering a recommendation, verify:

- [ ] Do I understand the company's industry and business model?
- [ ] Do I know which features are enabled?
- [ ] Do I know what customizations exist?
- [ ] Have I seen the relevant metadata?
- [ ] Can I reproduce the issue with available information?
- [ ] Is my confidence level appropriate for the recommendation?

If any of these are uncertain, gather more information before proceeding.

## Related Documents

- [Problem Classification](problem-classification.md)
- [Company Profile](company-profile.md)
- [Solution Confidence](solution-confidence.md)