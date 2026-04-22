---
tags: [configuracion, viewtimanager, admin, grupos]
tipo: tecnica
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Groups

Groups in ViewtiManager make it easier to manage who gets which [[roles|roles]]. While roles define what actions and views a user can access, groups bundle users together so you can assign or change a role for many users at once. Groups are managed at **Admin → Groups**.

Groups are entirely internal to ViewtiManager — they do not affect the GUI directly, but they let you manage role assignments in bulk.

## Why Use Groups?

Without groups, changing role assignments for a team of 10 users requires editing each user record individually. By placing users in a group (e.g., `Log-Admins`), you assign the role once at the group level and all members inherit it instantly.

Groups are optional but highly recommended for:
- Large deployments with many users
- Teams that need frequent role changes
- Environments with [[active-directory|Active Directory]] integration where AD groups map to Viewtinet roles via [[ad-groups-roles]]

## Creating a Group

1. In the left sidebar, click **Admin**.
2. Select the **Groups** tab.
3. Click **+ ADD NEW** at the bottom of the group list.

### Group Details

| Field | Description |
|---|---|
| Name | Unique identifier (e.g., `Log-Analysts`) |
| Description | Optional notes on the group's purpose |

### Assigning Roles to the Group

1. Expand the **Group Roles** section.
2. In the Available column, check the box next to each [[roles|role]] you want this group to inherit.
3. Click the single-arrow **>** button to move roles to Selected.
4. Click **Save Changes**.

## Membership Behavior

When you add or remove a [[users|user]] from a group, they immediately gain or lose every role assigned to that group — no further edits are needed on their individual user account.

## Groups and External Identity Providers

When using [[active-directory|Active Directory]], AD security groups can be mapped to Viewtinet roles through the [[ad-groups-roles|AD Groups & Roles]] configuration. For [[ldap-integration|LDAP]], a single default role is assigned at login; group-based role mapping is not supported for LDAP.

## Related Pages

- [[roles]] — Permission sets assigned to groups
- [[users]] — Individual user accounts and group membership
- [[ad-groups-roles]] — Mapping Active Directory groups to Viewtinet roles
- [[tenants]] — Multi-tenancy and data isolation
