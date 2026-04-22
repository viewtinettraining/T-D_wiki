---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Active Directory Integration Guide PDF — Source Summary'
id: POQ-FOI-0AM-W0J
slug: ad-integration-pdf
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Active Directory Integration Guide PDF — Source Summary

This page summarizes the Active Directory Integration Guide (v6.3), covering how to connect [ViewtiManager](../productos/viewtimanager-overview.md) to an Active Directory (AD) domain for centralized authentication and role-based access control.

## Prerequisites

Before configuring AD integration, the following must be in place:

- A dedicated AD service account (e.g., `viewtinet_user`) with read access to the directory tree and a non-expiring password
- **TCP port 389** open between ViewtiManager and the AD server (standard LDAP)
- AD groups pre-created in the appropriate Organizational Units (OUs)
- Required domain information: Domain Name, Domain Controller IP/Hostname, Base DN, Bind DN
- NTP time synchronization between ViewtiManager and the AD server to prevent authentication failures

## Role Mapping

[Roles](../configuracion/roles.md) in ViewtiManager are mapped to AD groups by matching role names exactly to AD group names. The [Active Directory](../integraciones/active-directory.md) group membership determines which Viewtinet role a user receives.

Permission structure: `Module_Menu_Tab_Permission`, where:
- `VM` = ViewtiManager, `VS` = ViewtiSight
- Predefined permissions: `VS_FULL_ACCESS`, `VM_FULL_ACCESS`, `VS_READ_ONLY`

Example role-to-group mapping used in the guide:

| AD Group | Viewtinet Role | Access Level |
|----------|---------------|-------------|
| Admins_Viewtinet | Admin_Viewtinet | Full VM + VS access |
| Viewtisight_Viewtinet | Viewtisight_Viewtinet | VS full access only |
| ReadOnly_Viewtinet | ReadOnly_Viewtinet | VS read-only (no dashboard creation) |

## Integration Steps

1. Log in to ViewtiManager at `http://x.x.x.x:5000` (HTTP) or `https://x.x.x.x:5001` (HTTPS)
2. Go to **Admin > AUTH** tab > **AD Servers** section
3. Enter domain name, DC hostname/IP, Base DN, Bind DN, and service account credentials
4. Use **Authorized Branches** to map each AD group (with its OU) to a Viewtinet role
5. Save configuration

## GUI Access for AD Users

AD users access Viewtinet at port `4200` (HTTP) or `4201` (HTTPS). Credentials are their AD username and password. Role-based UI restrictions apply immediately upon login.

## Related Pages

- [Active Directory](../integraciones/active-directory.md) — AD integration concept page
- [Ldap Integration](../integraciones/ldap-integration.md) — LDAP alternative
- [Roles](../configuracion/roles.md) — role configuration
- [Users](../configuracion/users.md) — user management
- [Mfa Configuration](../integraciones/mfa-configuration.md) — multi-factor authentication
- [Viewtimanager Overview](../productos/viewtimanager-overview.md) — ViewtiManager module
