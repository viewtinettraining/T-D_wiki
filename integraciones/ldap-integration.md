---
title: "LDAP Integration"
description: "viewtiauth manages multiple authentication backends in Viewtinet, and LDAP is one of the supported external directory services. Integrating an LDAP server al..."
keywords: "integraciones, autenticacion"
---

# LDAP Integration

[Viewtiauth](viewtiauth.md) manages multiple authentication backends in Viewtinet, and LDAP is one of the supported external directory services. Integrating an LDAP server allows users to log in with their corporate credentials and be auto-provisioned on first login.

## Prerequisites

Before configuring LDAP, ensure the following requirements are satisfied:

**Service Account**
A dedicated LDAP user account must exist with read access to the directory tree. The account should have a non-expiring password to prevent authentication interruptions. A typical username is `viewtinet_user`, and the full bind DN would be `CN=viewtinet_user,DC=viewtinet,DC=local`.

**Network and Firewall**
Open the following TCP ports between the Viewtimanager host and the LDAP server:
- TCP 389 — standard LDAP (non-secure)
- TCP 636 — LDAPS (secure mode)

**LDAP Server Information**
Gather the following details in advance:
- Domain name (e.g., `viewtinet.local`)
- LDAP server IP or hostname
- Base DN (e.g., `DC=viewtinet,DC=local`)
- Admin Access DN (service account DN)

**Time Synchronization**
Both Viewtimanager and the LDAP server must have synchronized clocks. Time drift causes authentication failures. See [Os Setup](../instalacion/os-setup.md) for NTP configuration guidance.

**Default Role**
Unlike [Active Directory](active-directory.md) integration, LDAP does not support group-to-role mapping. All LDAP users receive a single default [role](../configuracion/roles.md) on first login. Create the role beforehand if a custom one is needed.

## Configuration Steps

1. Navigate to **Admin → Auth** in the [admin interface](../configuracion/gui-overview.md).
2. In the **Viewtiauth Integrations** section, locate the `ldap` row and check the **Active** box.
3. Select a **Default Role** from the dropdown for the `ldap` entry (e.g., `My_Role_4_LDAP`).
4. Scroll to the **LDAP Servers** section and click **+ ADD NEW LDAP SERVER**.
5. Fill in the connection parameters:
   - **IP Address**: LDAP server IP
   - **Port**: `389` (or `636` for LDAPS)
   - **Base DB**: directory base DN (e.g., `dc=viewtinet,dc=local`)
   - **Admin Access DN**: bind DN (e.g., `cn=admin,dc=viewtinet,dc=local`)
   - **Admin Password**: password for the bind account
   - **Unique User Field**: LDAP attribute used for username lookup (e.g., `uid`)
6. Click **SAVE CHANGES** to apply.

## Post-Configuration

LDAP users are auto-provisioned with the selected default role on first login. To assign a different role to a specific user, go to **Admin → [Users](../configuracion/users.md)** or **Admin → [Groups](../configuracion/groups.md)** after the account has been created.

The authentication order among backends is controlled through [Viewtiauth](viewtiauth.md), where each provider is assigned an Order value and can be enabled or disabled independently.

See also [Mfa Configuration](mfa-configuration.md) for adding a second authentication factor on top of LDAP credentials.
