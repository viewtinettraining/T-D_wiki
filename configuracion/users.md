---
tags: [configuracion, viewtimanager, admin, usuarios]
tipo: tecnica
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Users

The ViewtiManager Users page lets administrators create, manage, and audit local user accounts — whether they are administrators, [[viewtisight-overview|ViewtiSight]] analysts, or ViewtiLog operators. Users are managed at **Admin → Users**.

When Viewtinet is integrated with [[active-directory|Active Directory]] or [[ldap-integration|LDAP]], users can be auto-provisioned on first login without manual entry.

## Creating a New User

1. In the left sidebar, click **Admin**.
2. Select the **Users** tab.
3. Click **+ ADD NEW** at the bottom of the user list.

### Basic User Details

| Field | Description |
|---|---|
| Username | Unique login name (e.g., `jdoe`, `analyst1`) |
| Password | Must meet the password policy (see below) |
| Repeat Password | Must match the Password field exactly |
| Email | Required for [[mfa-configuration|MFA]] code delivery |
| Tenant | Assign to a [[tenants|tenant]] if using multi-tenant mode |
| Name / Last Name | Optional full name fields for reference |

### Password Policy

- Minimum **12** characters
- At least **1 digit** (0–9)
- At least **1 uppercase** letter (A–Z)
- At least **1 special** character (`! " @ # $ % ^ & * ( )`)

## Account Flags

| Flag | Effect |
|---|---|
| Two Factor Authentication | Sends a one-time code via email on each login. Requires valid email and tenant. |
| Password changed | Uncheck to force password change on first login. |
| Logged in | Indicates active session. Uncheck to immediately log the user out. |
| Session Never Expires | Grants an immortal session with no automatic timeout. |

## Assigning Groups and Roles

- **Groups** (optional) — bundle users for bulk role management. See [[groups]].
- **Roles** (required) — define what the user sees and can do in the GUI. At least one role is mandatory. See [[roles]].

Every user must have at least one role to log in or view any dashboards. Use the dual-list selector to move available roles to selected.

## Tips

- Groups simplify bulk role changes: update a group's roles once and all members inherit the change immediately.
- Use the **Logged in** flag to immediately terminate a user's active session after a suspected credential leak.
- Limit **Session Never Expires** to service or machine accounts only.

## Related Pages

- [[roles]] — Role-based access control and permission sets
- [[groups]] — Group-based user management
- [[tenants]] — Multi-tenant configuration
- [[mfa-configuration]] — Multi-factor authentication setup
- [[active-directory]] — Active Directory user auto-provisioning
