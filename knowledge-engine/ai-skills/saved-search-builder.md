# AI Skill: Saved Search Builder

## Purpose

This skill teaches an AI how to build Saved Searches using structured reasoning. The goal is not to memorize templates but to learn the decision process an experienced NetSuite consultant uses when designing a search from a business requirement.

## Skill Flow

```
Business Requirement
       ↓
   1. Determine if a Saved Search is appropriate
       ↓
   2. Gather customer context
       ↓
   3. Collect metadata
       ↓
   4. Select the record type
       ↓
   5. Design criteria
       ↓
   6. Design results
       ↓
   7. Build formulas (if needed)
       ↓
   8. Optimize performance
       ↓
   9. Validate results
       ↓
  10. Explain the design
       ↓
  11. Consider alternative approaches
       ↓
  Deliverable
```

---

## Step 1: Determine If a Saved Search Is Appropriate

Before building a search, confirm that a saved search is the right tool for the requirement.

### Saved Search Decision Tree

```
What does the user need?
  │
  ├── "I need a real-time dashboard" → SuiteAnalytics Workbook or Dashboard Portlet
  │
  ├── "I need a printed report" → Saved Search (if simple) or SuiteAnalytics (if formatted)
  │
  ├── "I need to monitor exceptions daily" → Saved Search with email schedule
  │
  ├── "I need to export data for analysis" → Saved Search with CSV export
  │
  ├── "I need ad-hoc analysis" → SuiteAnalytics Workbook
  │
  ├── "I need transaction-level detail" → Saved Search
  │
  └── "I need summarized KPIs" → Saved Search (summary type) or KPI portlet
```

### When a Saved Search Is the Right Choice

| Requirement | Recommendation |
|---|---|
| List of transactions matching criteria | Saved Search |
| Daily email alert for exceptions | Saved Search with schedule |
| Export for external system | Saved Search with CSV |
| Simple dashboard portlet | Saved Search |
| Summary by customer/vendor/item | Saved Search (summary type) |

### When Another Tool Is Better

| Requirement | Better Tool | Why |
|---|---|---|
| Formatted, printable report | SuiteAnalytics Workbook | Better layout and formatting |
| Interactive analysis | SuiteAnalytics Workbook | Drill-down, filtering, charting |
| Real-time dashboard | Dashboard / KPIs | Live portlets update automatically |
| Complex calculations across multiple data sources | SuiteAnalytics Workbook (Dataset + Workbook) | Multi-source joins, richer formulas |

---

## Step 2: Gather Customer Context

Ask the business user the following questions. Do not skip this step — most search errors come from misunderstanding the requirement.

### Business Objective

| Question | Purpose |
|---|---|
| "What business question are you trying to answer?" | Defines the purpose |
| "Who will use this search?" | Determines audience and sharing |
| "How often will it be run?" | Determines schedule vs. ad-hoc |
| "What decision will this search inform?" | Determines what data is needed |

### Data Requirements

| Question | Purpose |
|---|---|
| "What type of data is this?" | Transactions, items, customers, vendors |
| "What specific records should be included?" | Defines the record type |
| "What time period should it cover?" | Defines date range |
| "What fields should be visible?" | Defines results columns |
| "What is the most important filter?" | Defines primary criteria |

### Expected Outcome

| Question | Purpose |
|---|---|
| "How many results do you expect?" | Validates criteria correctness |
| "Can you describe a sample result?" | Confirms understanding |
| "What does success look like?" | Defines acceptance criteria |

**Prompt pattern**:
```
The user needs [business objective]. 
The data source is [record type]. 
The key filters are [criteria]. 
The expected results are [description]. 
The audience is [users or roles].
```

---

## Step 3: Collect Metadata

Before designing the search, verify the metadata exists.

### Essential Metadata

| Metadata | Why Needed |
|---|---|
| **Field names and IDs** | Required for criteria, results, and formulas |
| **Custom field definitions** | Custom fields may not be visible to all roles |
| **Standard field availability** | Not all fields are available on all record types |
| **Record type relationships** | Required for joins (customer → sales order) |
| **User role permissions** | Determines what data the user can see |

### How to Collect Metadata

Ask the customer:
- "What fields do you see on the transaction record that relate to your question?"
- "Could you share a screenshot of the transaction record showing the fields you want?"
- "Are there any custom fields involved?"
- "What is the exact name of the field as it appears in NetSuite?"

### Common Metadata Pitfalls

| Pitfall | Impact |
|---|---|
| Assuming a field name matches the internal ID | Formula fields use internal IDs, not display names |
| Not checking the field is available on the record type | Some fields appear on forms but are not available in searches |
| Not verifying custom field access | Custom fields may be restricted by role |
| Not checking the field is indexed | Non-indexed fields slow down search performance |

---

## Step 4: Select the Record Type

### Record Type Decision Tree

```
Is the data about transactions or entities?
  │
  ├── Transactions → Select the transaction type
  │   ├── Sales Orders → Transactions, Sales Order
  │   ├── Purchase Orders → Transactions, Purchase Order
  │   ├── Item Fulfillments → Transactions, Item Fulfillment
  │   ├── Invoices → Transactions, Invoice
  │   └── All Transactions → Transactions, Transaction
  │
  ├── Items → Lists, Items
  │
  ├── Customers → Lists, Relationships, Customers
  │
  ├── Vendors → Lists, Relationships, Vendors
  │
  ├── Employees → Lists, Employees
  │
  └── Other → Select the appropriate list or type
```

### Common Record Types by Module

| Module | Primary Record Types |
|---|---|
| Sales | Sales Order, Invoice, Item Fulfillment, Cash Sale, Estimate |
| Purchasing | Purchase Order, Vendor Bill, Item Receipt, Vendor Return |
| Inventory | Inventory Item, Inventory Transfer, Inventory Adjustment |
| Manufacturing | Assembly Item, Work Order, BOM Revision |
| Accounting | Journal Entry, GL Account, Subsidiary |

### When to Use "Transaction" vs. Specific Type

| Situation | Record Type |
|---|---|
| Need data from all transaction types | Transaction |
| Need only sales orders | Sales Order |
| Need to compare POs and SOs together | Transaction (with type filter) |
| Need specific fields only available on one type | Specific type |

---

## Step 5: Design Criteria

Criteria define what data is included in the search results.

### Criteria Design Framework

1. **Start with the most restrictive filter** — This reduces the dataset immediately and improves performance
2. **Use AND by default** — OR conditions should be used intentionally
3. **Date ranges are the primary filter** — Most searches need a date range
4. **Use Contains rather than Start With** — Contains is more flexible (but slower on non-indexed fields)
5. **Avoid negative conditions where possible** — NOT conditions can be slower

### Criteria Construction Decision Tree

```
What is the primary filter?
  │
  ├── Date → Use a date range (Current Fiscal Quarter, Last Month, Custom)
  │
  ├── Status → Select the appropriate status values
  │
  ├── Type → Select the transaction type(s)
  │
  ├── Customer/Vendor/Item → Select from the list
  │
  └── Custom field → Verify the field exists and is indexed
```

### Criteria Pattern Examples

| Business Requirement | Criteria Pattern |
|---|---|
| Show open sales orders from last month | Date = Last Month, Status = Open |
| Show overdue purchase orders | Expected Date = Before Today, Status ≠ Fully Received |
| Show items with negative on-hand | On Hand = less than 0 |
| Show customers with no activity in 6 months | No criteria on customers; use a joined search or criteria |
| Show POs over $10,000 | Total = greater than 10,000 |

### Common Criteria Mistakes

| Mistake | Why It Happens | Fix |
|---|---|---|
| Too many OR conditions | Trying to include too many variations | Use IN instead of multiple ORs |
| Missing date range | Returns all historical data | Always add a date range |
| Using wrong operator | Is vs. Contains vs. Start With | Test with a small sample |
| Over-filtering | Too many criteria that exclude valid results | Start minimal, add incrementally |

---

## Step 6: Design Results

Results define what columns appear in the search output.

### Results Design Framework

1. **Include only the fields needed** — Extra columns slow performance and confuse readers
2. **Order columns logically** — Group related fields (identification, dates, amounts, classifications)
3. **Use meaningful column labels** — Custom labels clarify the output (especially for formulas)
4. **Consider the output format** — Summary type vs. list type affects what fields are available
5. **Use sorting to improve readability** — Sort on the most meaningful column

### Standard Result Patterns

| Use Case | Standard Columns |
|---|---|
| **Order tracking** | Document Number, Date, Customer, Total, Status, Ship Date, Memo |
| **Inventory status** | Item Name, Location, On Hand, Available, Committed, Reorder Point |
| **Customer activity** | Customer Name, Last Order Date, Total Revenue, Balance |
| **Vendor performance** | Vendor Name, PO Count, Total Spend, On-Time % |
| **Aging analysis** | Document Number, Due Date, Days Overdue, Amount, Customer |

### Summary Type Results

When using summary types:

| Summary Type | Use When |
|---|---|
| **Sum** | Total amounts by group (total revenue by customer) |
| **Count** | Count of records (number of orders per month) |
| **Average** | Average values (average order value by customer) |
| **Minimum** | First/earliest value (oldest invoice date) |
| **Maximum** | Latest value (most recent order date) |
| **Group** | Used for grouping — not displayed in results |

### Sorting Strategy

| Sort Order | Best For |
|---|---|
| Date descending | Most recent transactions first (most common) |
| Amount descending | Largest transactions first |
| Customer ascending | Alphabetical grouping |
| Status + Date | Operational tracking by status, then age |

---

## Step 7: Build Formulas

Formulas extend saved searches beyond standard fields.

### Formula Selection Decision Tree

```
Can the requirement be met with standard fields?
  ├── Yes → Use standard fields in Results tab
  │
  └── No → Does it need a calculation?
              ├── Numeric calculation → Formula (Numeric)
              ├── Text transformation → Formula (Text)
              ├── Currency calculation → Formula (Currency)
              ├── Date calculation → Formula (Date)
              ├── Percentage → Formula (Percent)
              └── Conditional text → Formula (Text) with CASE expression
```

### Formula Building Checklist

- [ ] Field IDs use internal IDs (e.g., `{amount}` not `Amount`)
- [ ] Field IDs are enclosed in curly braces
- [ ] Numeric formulas return numeric values, text formulas return text
- [ ] CASE expressions have complete WHEN/THEN/ELSE/END
- [ ] Parentheses are balanced
- [ ] String values are enclosed in single quotes
- [ ] NULL values are handled
- [ ] The formula is tested with a small dataset

### Common Formula Patterns

| Requirement | Formula |
|---|---|
| **Margin calculation** | `({revenueamount} - {cogsamount}) / {revenueamount}` |
| **Order-to-ship days** | `{shipdate} - {orderdate}` |
| **Days overdue** | `{today} - {duedate}` |
| **Conditional status label** | `CASE WHEN {amount} > 10000 THEN 'Large' WHEN {amount} > 5000 THEN 'Medium' ELSE 'Small' END` |
| **Concatenate fields** | `{firstname} || ' ' || {lastname}` |
| **Extract month name** | `TO_CHAR({trandate}, 'Month')` |
| **Check for NULL** | `NVL({custcol_customfield}, 'N/A')` |

### Formula Troubleshooting

| Symptom | Likely Cause |
|---|---|
| Formula returns blank | Field ID is wrong, or the field is not available on this record type |
| Formula returns error | Syntax error — missing parenthesis, unclosed quote, wrong data type |
| Formula returns unexpected value | Logic error — operator precedence, missing CASE condition, wrong field |
| Formula is very slow | Non-indexed field in a non-summary search, or complex calculation on large dataset |

---

## Step 8: Optimize Performance

### Performance Optimization Checklist

- [ ] Is a summary search appropriate? If not, use a list search
- [ ] Are date range filters included? Unbounded date ranges slow searches
- [ ] Are indexed fields used for filtering? Non-indexed fields slow searches
- [ ] Are result columns limited to what is needed? Extra columns add overhead
- [ ] Is the search run on a schedule? If ad-hoc, consider limiting results
- [ ] Is filtering done in Criteria rather than Results? Criteria filters are applied before results

### Performance Decision Tree

```
Is the search running slowly?
  │
  ├── Is it a summary search?
  │   ├── Yes → Can it be a list search?
  │   │   ├── Yes → Convert to list search
  │   │   └── No → Minimize group fields, add date range
  │   │
  │   └── No → Are there date range filters?
  │       ├── Yes → Are indexed fields used in criteria?
  │       │   ├── Yes → Consider result limit
  │       │   └── No → Use indexed fields (document number, date, status)
  │       └── No → Add a date range
  │
  └── Are there too many results?
      ├── Yes → Add additional criteria to narrow results
      └── No → Check for complex formulas
```

### Common Performance Issues

| Issue | Cause | Fix |
|---|---|---|
| Search returns 100,000+ results | No date range or overly broad criteria | Add date range, restrict criteria |
| Summary search runs for minutes | Too many group fields | Reduce group fields, add date range |
| Formula search is slow | Non-indexed field in formula | Use indexed fields, or filter in criteria first |
| Search times out | Complex formula on large dataset | Add criteria to reduce dataset before formula evaluates |

---

## Step 9: Validate Results

### Validation Checklist

- [ ] Do the results match the expected count?
- [ ] Do the results include all expected records?
- [ ] Do the results exclude unexpected records?
- [ ] Are dates in the correct range?
- [ ] Are amounts correct?
- [ ] Are formulas calculating correctly?
- [ ] Are summary values accurate?
- [ ] Are column labels clear?
- [ ] Are results sorted reasonably?
- [ ] Does the search complete within acceptable time?

### Validation Method

1. Run the search with minimal criteria to confirm the record type is correct
2. Add one criterion at a time, verifying results after each addition
3. Compare the result count to an expected count
4. Spot-check individual results against the actual records
5. Test with a user who understands the data

### Common Validation Failures

| Failure | Likely Cause |
|---|---|
| Too many results | Criteria are too broad, OR instead of AND |
| Too few results | Criteria are too restrictive, wrong date range, wrong status |
| Wrong amounts | Currency field used in numeric formula, wrong field ID |
| Missing records | Records are in a different status, not in the user's role scope |
| Formulas return blanks | Field ID is wrong, field not available on this record type |

---

## Step 10: Explain the Design

When delivering the search, explain the design decisions.

### Explanation Structure

```
**Purpose**: [What the search is designed to do]

**Record Type**: [Why this record type was chosen]

**Criteria**: [What filters are applied and why]
- Filter 1: [Reason for inclusion]
- Filter 2: [Reason for inclusion]

**Results**: [What columns are displayed and why]
- Column 1: [Purpose]
- Column 2: [Purpose]

**Formulas** (if applicable):
- Formula 1: [What it calculates and why it is needed]

**Usage**: [How to run the search, how often, who can see it]

**Expected results**: [Approximate result count, what success looks like]
```

### Explanation Example

```
**Purpose**: Identify purchase orders that are overdue for receiving.

**Record Type**: Purchase Order — because this is about outstanding commitments to vendors.

**Criteria**:
- Expected Date = Before Today — only past-due deliveries
- Status ≠ Fully Received — exclude already-completed orders
- Status ≠ Closed — exclude cancelled or closed orders

**Results**:
- Document Number — for reference
- Vendor Name — to contact about the delay
- Expected Date — to see how overdue
- Amount — to prioritize by value
- Memo — for context

**Usage**: Run daily and share with the purchasing team. Emailed automatically at 7 AM.

**Expected results**: 10-30 overdue POs depending on the time of month.
```

---

## Step 11: Consider Alternative Approaches

### Alternative Solution Decision Tree

```
Could this requirement be met with a standard report?
  ├── Yes → Consider using an existing report instead
  │
  └── No → Could a SuiteAnalytics Workbook work better?
              ├── Yes → Recommend Workbook for ad-hoc analysis
              │
              └── No → Saved Search is the correct tool
```

### When to Recommend an Alternative

| This Requirement... | May Be Better Served By... |
|---|---|
| Needs drill-down and charting | SuiteAnalytics Workbook |
| Needs formatted output for presentation | SuiteAnalytics Workbook |
| Is a one-time analysis | SuiteAnalytics Workbook (easier to build) |
| Needs to pull from multiple record types | SuiteAnalytics Dataset + Workbook |
| Already exists in another format | An existing report or search |

### Confidence Scoring

After completing the search, assign a confidence level:

| Score | Criteria |
|---|---|
| **High** | Business requirement clear, metadata confirmed, all fields verified, formulas tested, validation passed |
| **Medium** | Business requirement clear, some metadata unconfirmed, formulas not fully tested |
| **Low** | Business requirement unclear, metadata incomplete, formulas untested |
| **Deferred** | Requirement may be better served by a different tool; provide alternative recommendation |

---

## Failure Modes

| Failure Mode | Symptoms | Recovery |
|---|---|---|
| **Wrong record type** | Results show no records or unexpected records | Verify the record type against the data the user needs |
| **Formula errors** | Blank or incorrect formula results | Test each field ID individually, check data types |
| **Performance problems** | Search takes too long or times out | Add date range, reduce criteria, convert to list search |
| **Role visibility issues** | User cannot see expected results | Check role permissions for the record type and fields |
| **Data timing issues** | Results don't include today's transactions | Check transaction posting status, time zone settings |

## Escalation Rules

Escalate when:
- The required fields include custom records or fields that require configuration review
- The search needs SuiteScript for calculations more complex than saved search formulas can handle
- The performance does not improve after optimization
- The user's requirement is better met by SuiteAnalytics or a custom script
- The metadata needed is not available from the customer

---

## Skill Summary: The Mental Model

Before building a saved search, an experienced consultant asks:

1. **"What exactly does the user need to know?"** — The business question, not the feature request
2. **"Is a saved search the right tool?"** — Could a report or workbook be better
3. **"What record type contains this data?"** — The foundation of the search
4. **"What is the most important filter?"** — The primary criteria
5. **"What columns tell the story?"** — The results that answer the question
6. **"Does this need a calculation?"** — Formulas should be the exception, not the rule
7. **"How will this be used?"** — Scheduled, dashboard, export — affects design choices
8. **"Who sees this?"** — Audience determines sharing and visibility settings
9. **"Is it fast enough?"** — Performance should match the expected use
10. **"Can I explain this to someone else?"** — If the design cannot be explained simply, it may be overcomplicated

## Related Documents

- [Saved Searches Learning Path](../../docs/saved-searches/README.md)
- [Saved Searches Support Intelligence](../support-intelligence/saved-searches-support.md)
- [Customer Context: Metadata Collection](../customer-context/metadata-collection.md)
- [Customer Context: Customer Interview Framework](../customer-context/customer-interview-framework.md)

## Oracle References

- [Oracle NetSuite Help Center: Saved Searches](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Saved Search Formulas](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Saved Search Performance](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)