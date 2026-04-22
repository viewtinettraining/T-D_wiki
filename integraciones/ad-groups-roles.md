---
title: "AD Groups and Roles Mapping"
description: "This page explains how to create ViewtiManager roles that map to Active Directory groups, enabling domain users to receive the correct access level automatic..."
keywords: "integraciones, viewtimanager, active-directory, roles, rbac"
---

# AD Groups and Roles Mapping

This page explains how to create [ViewtiManager roles](../configuracion/roles.md) that map to Active Directory groups, enabling domain users to receive the correct access level automatically upon login. The [AD integration](active-directory.md) must be configured before this step.

AD groups must already exist in Active Directory before creating the role mappings. The role name in ViewtiManager **must match** the AD group name exactly.

## Example AD Structure

For this guide, an OU named **Viewtinet_Users** contains three AD groups:

| AD Group | Intended Access |
|---|---|
| Admins_Viewtinet | Full access to ViewtiManager and ViewtiSight |
| Viewtisight_Viewtinet | Full access to ViewtiSight only, no ViewtiManager |
| ReadOnly_Viewtinet | Read-only access to ViewtiSight, no dashboard creation |

## Creating Roles for AD Groups

1. Log in to [ViewtiManager](../productos/viewtimanager-overview.md) as admin.
2. Click **Admin → Roles** and then **Add New**.
3. In the **Details** section, set the role **Name** to match the AD group name exactly (e.g., `Admins_Viewtinet`).
4. In **Role Permissions**, assign the appropriate permissions using the dual-list selector.
5. Click **SAVE**.

### Permission Assignments for the Example Groups

| Role Name | Assigned Permissions | Result |
|---|---|---|
| Admins_Viewtinet | `VS_FULL_ACCESS` + `VM_FULL_ACCESS` | Full access to both ViewtiManager and [ViewtiSight](../productos/viewtisight-overview.md) |
| Viewtisight_Viewtinet | `VS_FULL_ACCESS` | Full access to ViewtiSight only; ViewtiManager access denied |
| ReadOnly_Viewtinet | `VS_READ_ONLY` | Read-only ViewtiSight; no dashboard creation; ViewtiManager denied |

## Permission Naming Convention

Permissions follow the pattern **Module_Menu_Tab_Permission**:
- `VM` = ViewtiManager, `VS` = ViewtiSight
- `FILTERED` in the permission name means access to that area is **denied**
- Absence of `FILTERED` means access is **allowed**

Two predefined permissions grant complete access: `VS_FULL_ACCESS` and `VM_FULL_ACCESS`.

## Behavior at Login

Once the roles and [AD integration](active-directory.md) are configured, users log in at the Viewtiauth URL. ViewtiManager authenticates the user via AD, checks their AD group membership, and applies the matching role:

| User | AD Group | Role Applied | Behavior |
|---|---|---|---|
| user_admin_viewtinet | Admins_Viewtinet | Admin_Viewtinet | Full access to ViewtiManager and ViewtiSight |
| user_vs_viewtinet | Viewtisight_Viewtinet | Viewtisight_Viewtinet | Full ViewtiSight access; ViewtiManager denied |
| user_ro_viewtinet | ReadOnly_Viewtinet | ReadOnly_Viewtinet | Restricted ViewtiSight (no Composer); ViewtiManager denied |

## Important Notes

- Every AD group you want to authorize must have a corresponding [role](../configuracion/roles.md) in ViewtiManager with the exact matching name.
- The role name matching is case-sensitive.
- Repeat the role creation process for each AD group that requires platform access.

## Related Pages

- [Active Directory](active-directory.md) — AD integration setup and prerequisites
- [Roles](../configuracion/roles.md) — Role permissions and data set configuration
- [Viewtiauth](viewtiauth.md) — Authentication backend order and default roles
- [Users](../configuracion/users.md) — Manual user management
- [Groups](../configuracion/groups.md) — Internal Viewtinet groups for bulk role assignment
