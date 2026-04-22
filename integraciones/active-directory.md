---
title: "Active Directory Integration"
description: "ViewtiManager supports integration with Active Directory (AD), enabling domain users to authenticate and access the Viewtinet platform with their existing cr..."
keywords: "integraciones, viewtimanager, active-directory, autenticacion"
---

# Active Directory Integration

ViewtiManager supports integration with Active Directory (AD), enabling domain users to authenticate and access the Viewtinet platform with their existing credentials. This integration centralizes authentication and role assignments, streamlining user management. See [Ad Groups Roles](ad-groups-roles.md) for the role mapping procedure.

## Prerequisites

### 1. AD Service Account

Create a dedicated user account in the domain with the following properties:

- **Username** — unique service account (e.g., `viewtinet_user`)
- **Permissions** — read access to the AD structure to retrieve user and group information
- **Domain Scope** — access to the Organizational Units (OUs) where the relevant users are stored
- **Non-Expiring Password** — recommended to prevent authentication failures

### 2. Network and Firewall

| Port | Protocol | Use |
|---|---|---|
| TCP 389 | LDAP | Standard directory queries (non-secure) |
| TCP 636 | LDAPS | Secure directory queries (encrypted) |

### 3. Domain Controller Information

Gather before starting:
- **Domain Name** (e.g., `viewtinet.local`)
- **Domain Controller IP or Hostname** (e.g., `10.30.23.8` or `dc01.viewtinet.local`)
- **Base DN** (e.g., `DC=viewtinet,DC=local`)
- **Bind DN** (e.g., `CN=viewtinet_user,DC=viewtinet,DC=local`)

### 4. Time Synchronization

Both ViewtiManager and the AD server must have synchronized time settings. Time drift causes authentication failures.

## Configuration Steps

1. Log in to [ViewtiManager](../productos/viewtimanager-overview.md) as admin at `http://<ip>:5000` (HTTP) or `https://<ip>:5001` (HTTPS).
2. Click **Admin** in the left sidebar, then select the **Auth** tab.
3. In the [Viewtiauth Integrations](viewtiauth.md) section, enable the `ad` entry and set its **Default Role**.
4. Scroll down to the **AD Servers** section and fill in the connection fields (server IP, port, Base DN, Bind DN, password).
5. Click the pencil icon next to **Authorized Branches** to add the AD groups and their OUs.
6. Use **ADD NEW BRANCH** to insert each AD group and its OU.
7. Click **SAVE**.

## Authorized Branches

Authorized Branches define which AD groups are permitted to access the Viewtinet platform. Each branch maps an AD group to an OU. Only members of listed groups will be authenticated.

## User Auto-Provisioning

When an AD user logs in for the first time, their account is automatically created in ViewtiManager with the default role configured in [Viewtiauth](viewtiauth.md). You do not need to create these users manually in [Admin → Users](../configuracion/users.md).

## Testing the Integration

After configuration, test by logging in at `http://<ip>:4200` or `https://<ip>:4201` with an AD user's credentials. If the configuration is correct, the user is authenticated and shown options according to their assigned [role](../configuracion/roles.md).

## Related Pages

- [Ad Groups Roles](ad-groups-roles.md) — Mapping AD groups to Viewtinet roles
- [Viewtiauth](viewtiauth.md) — Authentication backends and precedence order
- [Roles](../configuracion/roles.md) — Role permission sets
- [Users](../configuracion/users.md) — Local user management
- [Mfa Configuration](mfa-configuration.md) — Multi-factor authentication
