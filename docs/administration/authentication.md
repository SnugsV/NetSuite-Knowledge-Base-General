---
title: Authentication
module: Administration
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Authentication

## Quick Summary

Authentication controls how users log in to NetSuite. Administrators configure password policies, login methods, IP address rules, and session settings to protect account access. This article covers the standard authentication options available to every NetSuite account.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Authentication is the process of verifying that a user is who they claim to be. In NetSuite, authentication happens at login — the user provides credentials, and the system validates them before granting access.

NetSuite supports multiple authentication methods:

- **Email and password** — The standard method, available to all accounts
- **Two-factor authentication (2FA)** — An additional security layer (covered in [Two-Factor Authentication](two-factor-authentication.md))
- **Single sign-on (SSO)** — Authentication through a corporate identity provider (covered in [Single Sign-On](single-sign-on.md))

## Password Policies

Password policies define the rules for user passwords. These are configured at:

```
Setup > Company > Password Policies
```

Configurable policies include:

| Policy | What It Controls |
|---|---|
| Minimum Length | The shortest allowed password (default: 8 characters) |
| Complexity Requirements | Whether passwords must include uppercase, lowercase, numbers, and special characters |
| Password History | How many previous passwords are remembered and cannot be reused |
| Maximum Age | How long a password is valid before it must be changed |
| Failed Login Attempts | How many failed attempts before the account is locked |
| Lockout Duration | How long the account remains locked after too many failed attempts |

## Session Settings

Session settings control how long a user remains logged in:

```
Setup > Company > Session Management
```

| Setting | What It Controls |
|---|---|
| Session Timeout | How long a session can remain idle before the user is automatically logged out |
| Maximum Session Length | The maximum duration of a login session |
| Concurrent Sessions | Whether a user can be logged in from multiple browsers or devices simultaneously |

## IP Address Rules

IP address rules restrict login to specific IP addresses or ranges. This is useful for organizations that want to require all NetSuite access to come through a corporate VPN.

```
Setup > Company > IP Address Rules
```

IP rules can be configured to:

- Allow login only from specific IP ranges
- Block login from specific IP ranges
- Require 2FA when logging in from unrecognized IP addresses
- Apply different rules for administrators vs. regular users

## Login Email

Each user logs in using their **login email**, which is set on the user record. This can differ from the user's personal email address and from the email used on their employee record.

To change a user's login email:

1. Go to **Setup > Users > Manage Users**
2. Select the user
3. Update the **Email** field
4. Save the user record

## Password Reset

Users can reset their own password from the login page by clicking **Forgot Password?**. Administrators can also trigger a password reset from the user record.

To reset a user's password:

1. Go to **Setup > Users > Manage Users**
2. Select the user
3. Click **Reset Password**
4. The user receives an email with reset instructions

## Login History

Administrators can review login history to identify suspicious activity:

```
Setup > Users > Login History
```

The login history shows:

- Date and time of each login
- IP address used
- Whether the login was successful
- The role used during the session

## Common Mistakes

- **Setting password policies too restrictively**: Overly complex requirements cause users to write down passwords or use password recovery frequently.
- **Not setting a session timeout**: Without a timeout, an unattended session remains accessible to anyone who uses that computer.
- **Allowing concurrent sessions when not needed**: Concurrent sessions increase the attack surface. Disable them unless users genuinely need to be logged in from multiple devices simultaneously.
- **Not reviewing login history**: Unusual login patterns can indicate compromised accounts. Review login history periodically.

## Best Practices

- Set password policies that balance security with usability (12-character minimum, moderate complexity).
- Enable session timeouts (15-30 minutes of inactivity is reasonable).
- Restrict concurrent sessions unless there is a clear business need.
- Use IP address rules to restrict access to known networks.
- Review login history monthly for unusual activity.
- Require administrators to use stronger authentication than regular users.

## Related Articles

- [Two-Factor Authentication](two-factor-authentication.md)
- [Single Sign-On](single-sign-on.md)
- [Users](users.md)
- [Security Best Practices](security-best-practices.md)

## Oracle References

- [Oracle NetSuite Help Center: Authentication](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)