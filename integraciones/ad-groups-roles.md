---
tags: [integraciones, viewtimanager, active-directory, roles, rbac]
tipo: tecnica
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# AD Groups and Roles Mapping

This page explains how to create [[roles|ViewtiManager roles]] that map to Active Directory groups, enabling domain users to receive the correct access level automatically upon login. The [[active-directory|AD integration]] must be configured before this step.

AD groups must already exist in Active Directory before creating the role mappings. The role name in ViewtiManager **must match** the AD group name exactly.

## Example AD Structure

For this guide, an OU named **Viewtinet_Users** contains three AD groups:

| AD Group | Intended Access |
|---|---|
| Admins_Viewtinet | Full access to ViewtiManager and ViewtiSight |
| Viewtisight_Viewtinet | Full access to ViewtiSight only, no ViewtiManager |
| ReadOnly_Viewtinet | Read-only access to ViewtiSight, no dashboard creation |

## Creating Roles for AD Groups

1. Log in to [[viewtimanager-overview|ViewtiManager]] as admin.
2. Click **Admin → Roles** and then **Add New**.
3. In the **Details** section, set the role **Name** to match the AD group name exactly (e.g., `Admins_Viewtinet`).
4. In **Role Permissions**, assign the appropriate permissions using the dual-list selector.
5. Click **SAVE**.

### Permission Assignments for the Example Groups

| Role Name | Assigned Permissions | Result |
|---|---|---|
| Admins_Viewtinet | `VS_FULL_ACCESS` + `VM_FULL_ACCESS` | Full access to both ViewtiManager and [[viewtisight-overview|ViewtiSight]] |
| Viewtisight_Viewtinet | `VS_FULL_ACCESS` | Full access to ViewtiSight only; ViewtiManager access denied |
| ReadOnly_Viewtinet | `VS_READ_ONLY` | Read-only ViewtiSight; no dashboard creation; ViewtiManager denied |

## Permission Naming Convention

Permissions follow the pattern **Module_Menu_Tab_Permission**:
- `VM` = ViewtiManager, `VS` = ViewtiSight
- `FILTERED` in the permission name means access to that area is **denied**
- Absence of `FILTERED` means access is **allowed**

Two predefined permissions grant complete access: `VS_FULL_ACCESS` and `VM_FULL_ACCESS`.

## Behavior at Login

Once the roles and [[active-directory|AD integration]] are configured, users log in at the Viewtiauth URL. ViewtiManager authenticates the user via AD, checks their AD group membership, and applies the matching role:

| User | AD Group | Role Applied | Behavior |
|---|---|---|---|
| user_admin_viewtinet | Admins_Viewtinet | Admin_Viewtinet | Full access to ViewtiManager and ViewtiSight |
| user_vs_viewtinet | Viewtisight_Viewtinet | Viewtisight_Viewtinet | Full ViewtiSight access; ViewtiManager denied |
| user_ro_viewtinet | ReadOnly_Viewtinet | ReadOnly_Viewtinet | Restricted ViewtiSight (no Composer); ViewtiManager denied |

## Important Notes

- Every AD group you want to authorize must have a corresponding [[roles|role]] in ViewtiManager with the exact matching name.
- The role name matching is case-sensitive.
- Repeat the role creation process for each AD group that requires platform access.

## Related Pages

- [[active-directory]] — AD integration setup and prerequisites
- [[roles]] — Role permissions and data set configuration
- [[viewtiauth]] — Authentication backend order and default roles
- [[users]] — Manual user management
- [[groups]] — Internal Viewtinet groups for bulk role assignment
