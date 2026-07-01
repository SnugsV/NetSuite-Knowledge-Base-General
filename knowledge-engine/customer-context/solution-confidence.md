# Solution Confidence

## Purpose

Solution confidence determines how strongly the AI should recommend a solution and when additional evidence is required. Recommending a low-confidence solution can cause more harm than good.

## Confidence Levels

### High Confidence

| Criteria | Indicators |
|---|---|
| **Clear root cause** | The cause is visible and unambiguous |
| **Known fix** | The fix is documented and has been verified in similar environments |
| **Evidence matches** | All evidence supports the diagnosis |
| **Environment confirmed** | The customer's configuration matches the expected setup |
| **Reproducible** | The issue can be reproduced in a sandbox |

**Action**: Recommend the solution with clear instructions. State confidently that this should resolve the issue.

### Medium Confidence

| Criteria | Indicators |
|---|---|
| **Likely cause** | The cause is probable but not certain |
| **Standard fix** | The fix is standard but may not apply in this customer's environment |
| **Some evidence** | Evidence supports the diagnosis but is not comprehensive |
| **Configuration unknown** | Some configuration details have not been confirmed |

**Action**: Recommend the solution. Explain the reasoning. Add a verification step: "Try this and let me know if the issue persists."

### Low Confidence

| Criteria | Indicators |
|---|---|
| **Possible causes** | Multiple causes could explain the symptom |
| **Insufficient evidence** | Missing metadata, configuration, or transaction details |
| **Environment uncertain** | The customer's configuration is largely unknown |
| **Cannot reproduce** | The issue cannot be tested |

**Action**: Gather more information before recommending. Share the likely cause with the customer and explain what additional information is needed.

### Unknown

| Criteria | Indicators |
|---|---|
| **No clear cause** | The symptom does not map to any known pattern |
| **No evidence** | No metadata or transaction details available |
| **Environment unknown** | Nothing is known about the customer's configuration |

**Action**: Do not recommend a solution. Explain what information is needed and escalate if appropriate.

## Confidence Decision Tree

```
Has the root cause been clearly identified?
  ├── Yes → Is there a documented fix?
  │         ├── Yes → Does the customer's environment match the expected configuration?
  │         │         ├── Yes → HIGH confidence
  │         │         └── No → MEDIUM confidence
  │         └── No → MEDIUM confidence (document the limitation)
  │
  └── No → Is there a likely cause with supporting evidence?
            ├── Yes → MEDIUM confidence
            │
            └── No → Is there any information at all?
                        ├── Yes → LOW confidence
                        └── No → UNKNOWN
```

## When to Downgrade Confidence

| Situation | Confidence Change | Reason |
|---|---|---|
| Customer has significant customizations | High → Medium | Customizations may override standard behavior |
| Customer has not confirmed configuration | Medium → Low | Assumptions about configuration may be wrong |
| Issue only happens intermittently | Medium → Low | Intermittent issues are harder to diagnose |
| Customer cannot reproduce in sandbox | Medium → Low | Cannot verify the fix before applying |
| Multiple modules are affected | High → Medium | Cross-module issues may have multiple causes |

## Communication by Confidence Level

| Level | What to Say |
|---|---|
| **High** | "Based on the information you've provided, I'm confident the issue is X. Here's the recommended fix: [steps]. Please try this and let me know the result." |
| **Medium** | "The most likely cause is X. I recommend trying [fix]. If this doesn't resolve the issue, please share [additional information] and we'll investigate further." |
| **Low** | "I have some ideas about what might be happening, but I need more information to be certain. Could you please provide [specific metadata]? In the meantime, here is a possible workaround." |
| **Unknown** | "I don't have enough information to make a confident recommendation. Let's start by gathering [specific information], and I'll be able to help more effectively." |

## Related Documents

- [Customer Interview Framework](customer-interview-framework.md)
- [Metadata Collection](metadata-collection.md)
- [Escalation Intelligence](escalation-intelligence.md)
- [CUSTOMER_CONTEXT_REASONING.md](CUSTOMER_CONTEXT_REASONING.md)

## Oracle References

- [Oracle NetSuite Help Center: Support Resources](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)