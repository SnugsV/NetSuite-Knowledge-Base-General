---
title: Sandbox and Release Preview
module: Administration
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Sandbox and Release Preview

## Quick Summary

A sandbox is a copy of your NetSuite production account used for testing. Release Preview is a pre-release environment where you can test upcoming NetSuite features before they reach your production account. Both are essential for safe configuration changes and upgrade preparation.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Making changes directly in production is risky. A misconfigured permission, an incorrectly enabled feature, or a form modification can affect every user in the account. Sandboxes provide a safe environment to test changes before applying them to production.

NetSuite offers two types of non-production environments:

| Environment | Purpose | Data |
|---|---|---|
| **Sandbox** | Testing configuration changes, customizations, and integrations | Copy of production data (or empty) |
| **Release Preview** | Testing upcoming NetSuite releases | Separate from your account |

## Sandbox Types

NetSuite offers several sandbox types, depending on the account edition:

| Type | Description | Best For |
|---|---|---|
| **Standard Sandbox** | Full copy of production data at the time of refresh. Refreshed on request. | General testing, configuration changes, form customization |
| **Premium Sandbox** | Larger storage, more frequent refresh options, dedicated environment | Performance testing, large data sets, complex integrations |
| **Developer Sandbox** | Lightweight environment for SuiteScript development | Script development, unit testing |
| **Test Drive** | 30-day trial environment | Evaluation, training |

## Getting a Sandbox

Sandboxes must be purchased as an add-on to your NetSuite account. Contact your NetSuite account manager to add a sandbox.

Once purchased, sandbox access is configured at:

```
Setup > Company > Sandbox Setup
```

## Refreshing a Sandbox

When you refresh a sandbox, NetSuite copies the current state of your production account to the sandbox, overwriting any data or changes in the sandbox.

What happens during a refresh:

- Production data is copied to the sandbox
- All sandbox-specific configurations are overwritten
- SuiteScript deployments are suspended
- Integrations pointing to the sandbox URL remain active
- The refresh typically takes several hours

Refreshing is useful when you want to test with current production data. However, it destroys any changes made in the sandbox since the last refresh.

## Working in a Sandbox vs. Production

| Activity | In Sandbox | In Production |
|---|---|---|
| Feature enablement | Safe to test | Risky without testing |
| Role and permission changes | Safe to test | Risky without testing |
| Form customization | Safe to test | Can be tested, but affects users |
| SuiteScript development | Recommended | Use sandbox first |
| Data import testing | Recommended | Use sandbox for format testing |
| User training | Ideal | Not recommended |
| Daily operations | No | Yes — sandbox data is not real |

## Release Preview

NetSuite releases major updates twice per year (typically in February and August). Release Preview allows administrators to:

- Log in to a preview of the next release in advance
- Test their account's behavior with the new features
- Identify and address breaking changes before they reach production
- Train users on new functionality before it goes live

Release Preview is available approximately 6-8 weeks before each major release. Access it from:

```
Setup > Company > Release Preview
```

## Testing Checklist

Before and after each sandbox refresh or testing session:

- [ ] Document the specific tests to be performed
- [ ] Record the production state of each configuration being tested
- [ ] Execute tests methodically, documenting results
- [ ] Note any unexpected behavior
- [ ] After testing, either revert changes or apply them to production
- [ ] Schedule the next sandbox refresh

## Common Mistakes

- **Not using a sandbox at all**: Making configuration changes directly in production increases risk. Always use a sandbox for significant changes.
- **Making changes in the sandbox that are not documented**: If you cannot reproduce a configuration change in production, the sandbox test was wasted.
- **Forgetting to refresh the sandbox**: An old sandbox with outdated data is less useful for testing current configurations.
- **Not testing in Release Preview before each upgrade**: New releases can change behavior. Test in Release Preview before each upgrade cycle.
- **Sharing sandbox URLs externally**: Sandbox environments have different URLs than production. Sharing the wrong URL can cause confusion.

## Best Practices

- Use a sandbox for all configuration changes that affect multiple users.
- Refresh the sandbox before starting a new testing cycle.
- Document what you test and the results.
- Test SuiteScript changes in a developer sandbox before moving to a standard sandbox.
- Participate in each Release Preview cycle.
- Schedule sandbox testing during low-activity periods.
- Keep a list of sandbox-specific configurations (integrations, email settings) that need to be reconfigured after each refresh.

## Related Articles

- [Administration Overview](administration-overview.md)
- [Enabled Features](enabled-features.md)
- [Security Best Practices](security-best-practices.md)

## Oracle References

- [Oracle NetSuite Help Center: Sandbox](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Release Preview](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)