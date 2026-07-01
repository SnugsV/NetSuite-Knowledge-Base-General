# Administration Support Intelligence

## Common Customer Questions

| Question | Domain |
|---|---|
| "A user can't log in." | Authentication |
| "A user is missing menu options." | Permissions |
| "I can't enable a feature." | Feature enablement |
| "The system is running slowly." | Performance |
| "Two-factor authentication isn't working." | 2FA |
| "A role doesn't have the right access." | Role configuration |
| "The audit trail shows something unexpected." | Audit trail |

## Questions to Ask First

1. Which user or role is affected?
2. When did the problem start?
3. What exactly is the user trying to do?
4. Has this user ever been able to do this before?
5. Were there any recent changes to permissions, roles, or features?
6. Is this affecting one user or multiple users?

## Information Required Before Troubleshooting

- Username or email
- Role name
- Specific function or page that is not working
- Error message (if any)
- Browser and version
- Any recent admin changes

## Records to Inspect

| Symptom | Inspect This First |
|---|---|
| Can't log in | User record (active?), authentication method, password expiration, IP address restrictions |
| Missing menu options | User's role, role permissions, center assignment, feature availability |
| Can't enable feature | Feature dependencies, account edition, feature groups, existing data impact |
| Slow performance | System status, browser console errors, network latency, concurrent users |

## Common Root Causes

| Symptom | Most Likely Causes |
|---|---|
| Can't log in | 1. User is inactive. 2. Password expired. 3. IP address restricted. 4. 2FA misconfigured. 5. Account locked after multiple failed attempts. |
| Missing menu options | 1. Role does not include the required permission. 2. Feature is not enabled. 3. Center is not assigned. 4. Custom tab not configured. |
| Feature can't be enabled | 1. A prerequisite feature is not enabled. 2. Account edition does not include this feature. 3. Data exists that prevents enablement. |

## Support Conversation Pattern

**Customer says**: "I just created a new user but they can't see the Inventory menu."

**Interpretation**: The user has been created but their role does not include permissions for inventory functions, or the required feature is not enabled.

**Questions to ask**:
- What role was assigned to the user?
- What specific Inventory option are they looking for?
- Is the Inventory feature enabled?
- Can other users with the same role see the menu?

**Evidence required**: User role assignment, role permissions for Inventory, feature enablement status.

**Most likely causes**:
1. The assigned role does not include Inventory permissions
2. The Inventory feature is not enabled at the account level
3. The user needs a different role or center assignment

**Verification steps**:
1. Check the role's permissions for Inventory-related transactions
2. Check if Inventory features are enabled (Setup > Company > Enable Features)
3. Compare with a user who can access Inventory
4. Check center assignment on the role

**Recommended solution**:
- Add Inventory permissions to the role
- Enable Inventory features (if not already enabled)
- Assign a different role that includes Inventory access

**Escalate if**: The role has proper permissions, the feature is enabled, but the user still cannot see the menu. This may be a data or system issue.

## Related Saved Searches

- User roles and permissions
- Role permission matrix
- Feature enablement status
- Login history
- Audit trail by user

## Related Workflows

- User Creation Workflow
- Role Change Approval Workflow
- Feature Enablement Approval Workflow

## Related SuiteScript Considerations

- Custom roles may have programmatic permission restrictions
- SuiteScript initialization scripts may override menu visibility
- Custom center definitions may affect navigation

## Related Modules

- [All ERP modules] — feature enablement affects all modules
- [Saved Searches](../saved-searches/README.md) — permission-dependent visibility

## Escalation Criteria

Escalate when:
- Feature enablement requires SuiteCloud Plus or other add-on
- Custom role or center is not functioning as designed
- Performance issue is affecting multiple users
- Security concern (unauthorized access, audit trail anomalies)

## Oracle References

- [Oracle NetSuite Help Center: Administration](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: User Management](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: Role Management](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)