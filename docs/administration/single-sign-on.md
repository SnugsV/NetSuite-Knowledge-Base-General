---
title: Single Sign-On
module: Administration
difficulty: Advanced
estimated_time: 15 minutes
status: Draft
last_reviewed:
---

# Single Sign-On

## Quick Summary

Single sign-on (SSO) allows users to log in to NetSuite using their corporate identity provider credentials — typically Microsoft Entra ID (Azure AD), Okta, OneLogin, or another SAML 2.0 or OAuth 2.0 provider. SSO centralizes authentication management and can be combined with the identity provider's own 2FA policies.

## Difficulty

Advanced

## Estimated Time

15 minutes

## Overview

SSO shifts authentication from NetSuite to an external identity provider (IdP). When SSO is configured, users click a "Log In with SSO" button, are redirected to their organization's IdP login page, and upon successful authentication there, are redirected back to NetSuite already logged in.

NetSuite supports two SSO protocols:

- **SAML 2.0** — The most common SSO protocol. Supported by most enterprise identity providers.
- **OAuth 2.0 / OpenID Connect** — Newer protocol support available in recent NetSuite versions.

## How SSO Works

The SSO login flow:

1. User navigates to the NetSuite login page and clicks **Log In with SSO**
2. NetSuite redirects the user to the identity provider's login page
3. User authenticates with their corporate credentials (username, password, and potentially 2FA)
4. Identity provider sends a SAML assertion (an encrypted XML document) back to NetSuite
5. NetSuite validates the assertion and logs the user in

From the user's perspective, they log in once to their corporate system and can access NetSuite without entering separate credentials.

## Prerequisites

Before configuring SSO, verify:

- [ ] Your identity provider supports SAML 2.0
- [ ] You have administrator access to both NetSuite and the identity provider
- [ ] You know your NetSuite account ID
- [ ] You have a registered domain or can verify domain ownership
- [ ] Feature: SSO is enabled under **Setup > Company > Enable Features > SuiteCloud > SSO**

## Configuration Steps

### In NetSuite

1. Navigate to **Setup > Integration > SSO > SAML SSO Setup**
2. Download the NetSuite SAML metadata or note the ACS (Assertion Consumer Service) URL
3. Configure the IdP-initiated SSO URL and logout URL
4. Upload or paste the identity provider's SAML metadata
5. Configure SAML attribute mapping (which IdP field maps to the NetSuite email)
6. Enable SSO and save

### In the Identity Provider

1. Create a new application for NetSuite
2. Configure the ACS URL provided by NetSuite
3. Upload the NetSuite SAML metadata
4. Configure user attributes to include email
5. Set up user provisioning or group mapping if available
6. Test the SSO connection

## User Provisioning with SSO

SSO authenticates users but does not create them. Users must still be created in NetSuite first (see [Users](users.md)). However, many identity providers support **just-in-time provisioning**:

- When a new user authenticates via SSO, the IdP can send attributes that create the NetSuite user automatically
- This requires SCIM (System for Cross-Domain Identity Management) provisioning, supported by some identity providers
- Without SCIM, an administrator must create each user in NetSuite before they can log in via SSO

## Group Mapping

Some identity providers support role mapping through SAML attributes:

- The IdP sends a group membership attribute during authentication
- NetSuite maps the group to a specific role
- When a user's group membership changes in the IdP, their NetSuite role access changes automatically

This is useful for organizations with dynamic team structures where role changes should be reflected in NetSuite without manual updates.

## Combining SSO with 2FA

When SSO is configured, 2FA can be enforced at the identity provider level rather than in NetSuite:

- The identity provider handles all authentication, including 2FA
- NetSuite trusts the identity provider's assertion
- Users do not need to set up 2FA in NetSuite separately
- The identity provider's 2FA policies apply

This simplifies the user experience and centralizes security policy management.

## Common Mistakes

- **Not testing SSO with a sandbox first**: An SSO misconfiguration can lock all users out of the account. Always test in a sandbox.
- **Forgetting to keep a direct login method**: Before enabling SSO, ensure at least one user (typically an administrator) has a non-SSO login method as a fallback.
- **Not mapping user attributes correctly**: If the email attribute in the SAML assertion does not match the user's NetSuite email, authentication will fail.
- **Assuming SSO handles user provisioning**: SSO authenticates existing users — it does not create them unless SCIM is also configured.
- **Expiring SAML certificates without updating NetSuite**: When your IdP's SAML signing certificate expires, SSO login will stop working until the new certificate is uploaded to NetSuite.

## Best Practices

- Keep one administrative account with direct (non-SSO) login as a break-glass access method.
- Test SSO configuration thoroughly in a sandbox before enabling in production.
- Monitor SSO login failures in the audit trail during the first week after deployment.
- Set up SAML certificate expiry monitoring so certificates are renewed before they expire.
- Document the SSO configuration, including which IdP attributes map to which NetSuite fields.
- Train users on the SSO login flow — they need to know to click "Log In with SSO" rather than entering their password directly.

## Related Articles

- [Authentication](authentication.md)
- [Two-Factor Authentication](two-factor-authentication.md)
- [Security Best Practices](security-best-practices.md)
- [Enabled Features](enabled-features.md)

## Oracle References

- [Oracle NetSuite Help Center: Single Sign-On](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)
- [Oracle NetSuite: SAML SSO Configuration](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/)