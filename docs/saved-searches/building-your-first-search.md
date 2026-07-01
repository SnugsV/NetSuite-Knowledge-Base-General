---
title: Building Your First Search
module: Saved Searches
difficulty: Beginner
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Building Your First Search

## Quick Summary

Creating a Saved Search involves selecting a record type, defining criteria to filter records, choosing result columns to display, and saving the search for reuse. This article walks through the complete process with a practical example.

## Difficulty

Beginner

## Estimated Time

10 minutes

## Overview

We will build a Saved Search that answers a real business question: *"Which sales orders are still open and overdue?"* This is one of the most useful searches a company can have.

## Step-by-Step

### Step 1: Navigate to Saved Searches

```
Reports > Saved Searches > All Saved Searches > New
```

Alternatively, use Global Search: press **Ctrl+G**, type "New Saved Search," and select it from the results.

### Step 2: Choose the Search Type

Select **Transaction** as the search type. Why? Because we want to find sales orders, which are transactions.

NetSuite presents a list of available search types. If you know the exact record type, you can start typing to filter the list.

### Step 3: Name Your Search

Enter a clear, descriptive name:

```
Open Sales Orders — Overdue
```

A good name helps you find the search later and tells other users what it does.

### Step 4: Set Criteria

Criteria are the filters that determine which records appear in the results.

For our example:

1. In the **Criteria** subtab, click **Add**
2. Select **Type** → set it to **Sales Order**
3. Click **Add** again
4. Select **Status** → set it to **Pending Fulfillment** and **Pending Approval** (hold Ctrl to select multiple)
5. Click **Add** again
6. Select **Date Created** → set it to **on or before** and enter a date 30 days ago
7. Click **Add** again
8. Select **Main Line** → set it to **Yes** (we want one row per order, not per line item)

### Step 5: Choose Results

Results are the columns displayed in the output.

1. Go to the **Results** subtab
2. Add these columns in order:
   - **Document Number** — The sales order number
   - **Date Created** — When the order was entered
   - **Customer** — Who placed the order
   - **Status** — Current order status
   - **Total** — Order amount
   - **Days Overdue** — Formula: `{today} - {trandate}` (we will cover formulas in the Formulas article)
3. Set **Sort By** to **Date Created** ascending

### Step 6: Configure Available Filters

Available Filters allow users to refine the search without editing it.

1. Go to the **Available Filters** subtab
2. Add **Customer** — so users can filter by a specific customer
3. Add **Total** — so users can filter by order amount

### Step 7: Set Audience

1. Go to the **Audience** subtab
2. Select which roles should see this search
3. If you want it to be personal, leave this blank

### Step 8: Save and Test

Click **Save**. The search runs and displays your results.

Verify:

- Do you see only sales orders?
- Do they have the expected statuses?
- Are the date ranges correct?
- Do the columns display useful information?

If something is wrong, click **Edit** and adjust the criteria or results.

## The Search You Just Built

```
Search Type:  Transaction
Name:         Open Sales Orders — Overdue
Criteria:     Type = Sales Order
              Status = Pending Fulfillment OR Pending Approval
              Date Created = on or before 30 days ago
              Main Line = Yes
Results:      Document Number, Date Created, Customer, Status, Total, Days Overdue
              Sort by Date Created ascending
Available:    Customer, Total
```

## Next Steps

With this foundation, you can now:

- Add more criteria to narrow results further
- Add formula columns for calculated values
- Group results by customer or sales rep
- Save to a dashboard for daily monitoring

## Common Mistakes

- **Forgetting the Main Line filter**: Without it, transaction searches return one row per line item, mixing summary and detail data.
- **Choosing the wrong search type**: If you selected "Customer" instead of "Transaction," you could not filter by sales order status.
- **Not testing the search**: Always save and run before sharing. Check that results match expectations.
- **Using a vague name**: "Test Search" or "Search 1" are not useful. Name searches descriptively.

## Best Practices

- Give every search a descriptive, unique name.
- Add a short description explaining what the search does.
- Test with a known record to verify criteria are correct.
- Start simple and add complexity iteratively.
- Use Available Filters instead of creating multiple similar searches for different filter values.

## Related Articles

- [What Is a Saved Search?](what-is-a-saved-search.md)
- [Criteria](criteria.md)
- [Results](results.md)
- [Filters](filters.md)
- [Sorting](sorting.md)
- [Highlighting Results](highlighting-results.md)
- [Common Mistakes](common-mistakes.md)

## Oracle References

- [Oracle NetSuite Help Center: Creating Saved Searches](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Defining a Saved Search](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)