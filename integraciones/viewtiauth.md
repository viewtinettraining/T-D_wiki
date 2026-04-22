---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'ViewtiAuth Integrations'
id: K5S-FWW-XFQ-27A
slug: viewtiauth
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# ViewtiAuth Integrations

ViewtiAuth is the authentication orchestration layer in Viewtinet. It controls which authentication backends are active, the order in which they are tried, and what default [role](../configuracion/roles.md) is assigned to users upon successful login.

## Overview

The **Viewtiauth Integrations** section is found under **Admin → Auth** in the [administration interface](../configuracion/gui-overview.md). It presents a table of authentication entries, each defining one backend. Viewtiauth processes entries in ascending order by the **Order** field: `1` is highest priority.

If an entry is inactive, or authentication fails against its backend, Viewtiauth falls back to the next active entry in the list.

## Configuration Fields

| Field | Description |
|---|---|
| **Active** | Enables or disables this backend. Inactive entries are skipped entirely. |
| **Order** | Integer defining priority. Lower numbers are tried first. |
| **Type** | The authentication method to use for this entry. |
| **Default Role** | The [role](../configuracion/roles.md) automatically assigned to users authenticated via this backend. |

### Supported Authentication Types

- `local` — built-in Viewtinet user database, managed through [Users](../configuracion/users.md)
- `ad` — Microsoft Active Directory, configured via [Active Directory](active-directory.md)
- `ldap` — external LDAP server, configured via [Ldap Integration](ldap-integration.md)
- `saml2` — SAML 2.0 Identity Provider

## Authentication Flow

1. Viewtiauth reads all configured entries sorted by **Order** (ascending).
2. For each entry:
   - If **Active** is unchecked, skip to the next entry.
   - Otherwise, attempt authentication using the specified **Type**.
   - On success, assign the **Default Role** and grant access.
   - On failure, move to the next active entry.
3. If all active entries fail, authentication is denied.

### Example

| Order | Active | Type | Default Role |
|---|---|---|---|
| 1 | No | ad | — |
| 2 | Yes | local | Admin |
| 3 | Yes | ldap | Viewer |
| 4 | No | saml2 | — |

In this configuration, Viewtiauth tries the `local` backend first (order 2). If the user is not found or the password is wrong, it then tries `ldap` (order 3). The inactive `ad` and `saml2` entries are ignored.

## Role Assignment

The **Default Role** per entry determines what [permissions](../configuracion/roles.md) a newly provisioned user receives. For `local` users, [individual role](../configuracion/users.md) assignments can be modified afterward in **Admin → Users**. For LDAP users, role changes must be applied manually after account creation, as described in [Ldap Integration](ldap-integration.md).

For [Active Directory](active-directory.md), group-to-role mappings are available through [Ad Groups Roles](ad-groups-roles.md), allowing more granular control compared to LDAP's single default role.

## Multi-Factor Authentication

MFA is a separate layer applied on top of ViewtiAuth backends. See [Mfa Configuration](mfa-configuration.md) for setup details. MFA does not change the authentication order — it adds a second step after the primary backend succeeds.

## Notes

Changes to the authentication sequence affect all users immediately. Disabling or reordering entries without caution can inadvertently lock out administrative accounts. Always verify at least one active `local` entry is present before making changes, especially when configuring [Ldap Integration](ldap-integration.md) or [Active Directory](active-directory.md) for the first time.
