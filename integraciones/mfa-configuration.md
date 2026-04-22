---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'MFA Configuration'
id: 6RD-GGF-AW6-BD1
slug: mfa-configuration
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# MFA Configuration

Multi-Factor Authentication (MFA) adds a second security layer to the [Login](../configuracion/login.md) process in Viewtinet. After a successful primary authentication, users with MFA enabled receive a one-time code via email, which must be entered on a second screen before access is granted.

## How It Works

1. A user submits their credentials through the standard [Login](../configuracion/login.md) screen.
2. Viewtinet validates the primary credentials against the active backend configured in [Viewtiauth](viewtiauth.md).
3. If MFA is enabled for the account, the system sends a one-time code to the user's registered email address.
4. The user enters the code on the second authentication screen to complete login.

MFA operates on top of any authentication method — [LDAP](ldap-integration.md), [Active Directory](active-directory.md), or local users managed through [Users](../configuracion/users.md).

## Prerequisites

**SMTP Integration**
Outbound email must be configured before enabling MFA. Navigate to **Home → Configuration → Email Notifications** and set up your SMTP server. This is the channel through which one-time codes are delivered to users.

Without a working SMTP configuration, MFA codes cannot be sent and users will be unable to complete authentication.

## Configuring MFA

1. Go to **Admin → Auth** in the [administration interface](../configuracion/gui-overview.md).
2. Locate the **MFA Config** section.
3. Configure the following fields:

| Field | Description |
|---|---|
| Use script for MFA mailing | Optional. Check to use a custom shell script instead of the built-in mailer. |
| Sender Email | The From address for MFA emails. Replace the default `support@viewtinet.com` with your real mailbox, e.g., `mfa@yourdomain.com`. |
| Sender Name | Friendly name shown in the From field, e.g., `Security Team`. |

4. Click **Save Changes** at the bottom of the page.

## Custom Script Option

If your environment requires special email delivery logic, enable **Use script for MFA mailing**. This allows a shell script to handle the sending process instead of the built-in SMTP mailer. The script receives the recipient address and the one-time code as inputs.

## Relation to Other Auth Settings

MFA is configured globally under the Auth section but applies per-user. Administrators can enable or disable MFA for individual accounts via **Admin → [Users](../configuracion/users.md)**.

For organizations using role-based access, see [Roles](../configuracion/roles.md) for how user permissions are assigned. The overall authentication pipeline, including the order of backends tried, is defined in [Viewtiauth](viewtiauth.md).

For directory-based authentication that feeds into MFA, see [Ldap Integration](ldap-integration.md) or [Active Directory](active-directory.md).
