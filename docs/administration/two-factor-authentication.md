---
title: Two-Factor Authentication
module: Administration
difficulty: Intermediate
estimated_time: 10 minutes
status: Draft
last_reviewed:
---

# Two-Factor Authentication

## Quick Summary

Two-factor authentication (2FA) adds a second verification step to the login process, requiring both a password and a time-based one-time code from an authenticator app. 2FA significantly reduces the risk of unauthorized access from compromised passwords.

## Difficulty

Intermediate

## Estimated Time

10 minutes

## Overview

Standard authentication requires only a password. If that password is compromised — through phishing, data breaches, or weak password practices — an attacker can access the account. 2FA mitigates this risk by requiring a second factor: something the user possesses (their phone with an authenticator app).

NetSuite 2FA uses time-based one-time passwords (TOTP). The user installs an authenticator app (Google Authenticator, Microsoft Authenticator, Authy, or similar), links it to their NetSuite account, and enters the code displayed in the app when logging in.

## Enabling 2FA

2FA is controlled by account-level settings and enforced per user.

### Account-Level Setup

Navigate to **Setup > Company > Password Policies**. Under the 2FA section:

| Setting | Description |
|---|---|
| Require 2FA for All Users | Enforces 2FA for every user in the account |
| Require 2FA for Administrators | Enforces 2FA only for users with the Administrator role |
| Allow Users to Enroll | Permits users to set up 2FA voluntarily |

### User Enrollment

When 2FA is required or enabled, each user sets up their authenticator app:

1. Log in to NetSuite
2. Navigate to **Home > Set Preferences > 2FA**
3. Scan the QR code with their authenticator app
4. Enter the verification code from the app
5. Save the backup codes in a secure location

## Backup Codes

When a user enrolls in 2FA, NetSuite displays a set of backup codes. These are single-use codes that can be used to log in if the user loses access to their authenticator app.

Users should:

- Store backup codes in a secure password manager
- Keep them separate from their phone
- Generate new backup codes if the originals are used or compromised
- Keep at least one backup code accessible in case their phone is lost

Administrators can generate new backup codes from the user record if needed.

## Recovering 2FA Access

If a user loses their phone and does not have backup codes, an administrator can:

1. Go to **Setup > Users > Manage Users**
2. Select the user
3. Click **Reset 2FA**
4. The user can re-enroll with their new device

This should only be done after verifying the user's identity through an out-of-band channel (e.g., phone call, in-person verification).

## 2FA for Different Access Methods

2FA applies differently depending on how the user accesses NetSuite:

| Access Method | 2FA Behavior |
|---|---|
| Browser login | 2FA required at login |
| SuiteTalk (API) | Uses token-based authentication, not 2FA |
| SuiteCloud (SDF) | Uses token-based authentication |
| CSV Import | Uses password or token authentication |
| Email (inbound) | Not affected by 2FA |

API access through SuiteTalk and SuiteCloud uses separate authentication methods (OAuth tokens, TBA). 2FA is specifically for browser-based interactive sessions.

## Mandatory vs. Voluntary 2FA

| Approach | Pros | Cons |
|---|---|---|
| **Mandatory for all users** | Maximum security | Inconvenience for users, support burden for password resets |
| **Mandatory for administrators** | Protects highest-risk accounts | Non-admin accounts remain vulnerable |
| **Voluntary enrollment** | Minimal user friction | Low adoption rate |
| **IP-based conditional 2FA** | Good balance | Requires IP address rules configuration |

The recommended approach for most organizations is to require 2FA for administrators and highly encourage (or eventually require) it for all users.

## Common Mistakes

- **Not having a recovery plan for lost devices**: Without backup codes or an administrator reset process, a user with a lost phone can be locked out.
- **Enforcing 2FA without user communication**: Users need to know 2FA is coming, how to set it up, and how to save backup codes before it is enforced.
- **Not distinguishing between browser and API access**: 2FA does not affect API integrations, so there is no risk of breaking automated processes.
- **Assuming backup codes are stored securely**: Remind users that backup codes are as sensitive as passwords.

## Best Practices

- Require 2FA for all administrator roles.
- Communicate 2FA enforcement to users at least two weeks in advance.
- Provide instructions for setting up 2FA and saving backup codes.
- Test the 2FA recovery process before enforcing it widely.
- Keep the 2FA reset process documented for the support team.
- Review who has active 2FA enrollment during periodic security audits.

## Related Articles

- [Authentication](authentication.md)
- [Single Sign-On](single-sign-on.md)
- [Security Best Practices](security-best-practices.md)
- [Users](users.md)

## Oracle References

- [Oracle NetSuite Help Center: Two-Factor Authentication](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)