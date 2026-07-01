---
title: Security Best Practices
module: Administration
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Security Best Practices

## Quick Summary

Security in NetSuite requires a layered approach — strong authentication, least-privilege permissions, regular auditing, and proactive monitoring. This article consolidates security best practices from across the administration module into a single reference.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

NetSuite security is not a single feature or setting. It is the combination of multiple layers: how users authenticate, what roles they have, what permissions those roles grant, how changes are tracked, and how the account is monitored. A weakness in any layer reduces overall security.

## The Security Layers

### Layer 1: Authentication

| Practice | Why |
|---|---|
| Enforce strong password policies (12+ character minimum) | Reduces brute-force risk |
| Enable 2FA for all administrator accounts | Protects against credential theft |
| Consider SSO for centralized authentication | Simplifies access management |
| Set session timeouts (15-30 minutes) | Prevents unauthorized access to unattended sessions |
| Use IP address rules to restrict access | Limits login to trusted networks |

See [Authentication](authentication.md), [Two-Factor Authentication](two-factor-authentication.md), and [Single Sign-On](single-sign-on.md).

### Layer 2: Permissions

| Practice | Why |
|---|---|
| Follow the principle of least privilege | Users should have only the permissions they need |
| Start with View permissions and upgrade only when needed | Reduces the risk of accidental data modification |
| Review role assignments quarterly | Removes accumulated access from role changes |
| Never modify predefined roles — copy them first | Preserves the ability to reset to defaults |
| Limit the number of users with the Administrator role | The Administrator role has unrestricted access |

See [Permissions](permissions.md) and [Roles](roles.md).

### Layer 3: Feature Enablement

| Practice | Why |
|---|---|
| Only enable features that are actively needed | Every enabled feature adds attack surface and complexity |
| Test irreversible features in a sandbox first | Some features cannot be disabled |
| Review enabled features quarterly | Remove features that are no longer needed |
| Understand feature dependencies before enabling | A feature may automatically enable dependent features |

See [Enabled Features](enabled-features.md).

### Layer 4: Monitoring

| Practice | Why |
|---|---|
| Review the Audit Trail weekly or monthly | Identifies unusual activity early |
| Set up notifications for high-risk events | Role changes, permission modifications, new users |
| Review login history for failed attempts | Identifies brute-force attacks or compromised credentials |
| Investigate unusual patterns promptly | Early detection reduces damage |

See [Audit Trail](audit-trail.md) and [Authentication](authentication.md).

### Layer 5: Change Management

| Practice | Why |
|---|---|
| Test all configuration changes in a sandbox first | Prevents production disruptions |
| Document the reason for each configuration change | Helps future administrators understand decisions |
| Use Release Preview before each upgrade | Identifies breaking changes before they reach production |
| Maintain a change log for significant configuration changes | Provides audit trail for compliance |

See [Sandbox and Release Preview](sandbox-and-release-preview.md).

## Security Checklist

Use this checklist for periodic security reviews:

- [ ] No inactive user accounts remain active
- [ ] All administrator accounts have 2FA enabled
- [ ] Password policies require 12+ character minimum
- [ ] Session timeout is set to 30 minutes or less
- [ ] IP address rules are configured if the organization uses a VPN
- [ ] Administrator role is assigned to fewer than 5 users
- [ ] All custom roles follow least-privilege principles
- [ ] Audit Trail is reviewed at least monthly
- [ ] Login history is reviewed for unusual patterns
- [ ] Enabled features are reviewed and unused ones are disabled
- [ ] Sandbox is used for all configuration changes
- [ ] Release Preview is tested before each major upgrade

## Common Security Risks

| Risk | Mitigation |
|---|---|
| Compromised administrator credentials | 2FA for all administrators |
| Over-permissioned roles | Regular permission audits, least privilege |
| Unused active accounts | Quarterly user account review |
| Misconfigured features | Sandbox testing before production |
| Insider data access | Audit Trail monitoring, System Notes |
| API credential exposure | Token-based authentication with limited scope |

## Creating a Security Review Schedule

| Frequency | Activity |
|---|---|
| **Monthly** | Review Audit Trail, review login history, check for inactive users |
| **Quarterly** | Full permission audit, role review, feature enablement review |
| **Annually** | Comprehensive security review, password policy review, SSO certificate check |
| **Per Release** | Test Release Preview, update documentation for new features |

## Response Plan for Security Incidents

If you suspect a security incident:

1. **Isolate** — Temporarily deactivate the affected user account
2. **Investigate** — Review the Audit Trail and System Notes for the affected user
3. **Assess** — Determine what data was accessed or modified
4. **Remediate** — Reset passwords, revoke tokens, restore affected data
5. **Document** — Record the incident and response for future reference
6. **Review** — Update security practices to prevent recurrence

## Related Articles

- [Authentication](authentication.md)
- [Two-Factor Authentication](two-factor-authentication.md)
- [Single Sign-On](single-sign-on.md)
- [Permissions](permissions.md)
- [Roles](roles.md)
- [Audit Trail](audit-trail.md)
- [Sandbox and Release Preview](sandbox-and-release-preview.md)

## Oracle References

- [Oracle NetSuite Help Center: Security](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)