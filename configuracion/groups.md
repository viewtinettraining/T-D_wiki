---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Groups'
id: YPE-B1I-SE7-2QN
slug: groups
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Groups

Groups in ViewtiManager make it easier to manage who gets which [roles](roles.md). While roles define what actions and views a user can access, groups bundle users together so you can assign or change a role for many users at once. Groups are managed at **Admin → Groups**.

Groups are entirely internal to ViewtiManager — they do not affect the GUI directly, but they let you manage role assignments in bulk.

## Why Use Groups?

Without groups, changing role assignments for a team of 10 users requires editing each user record individually. By placing users in a group (e.g., `Log-Admins`), you assign the role once at the group level and all members inherit it instantly.

Groups are optional but highly recommended for:
- Large deployments with many users
- Teams that need frequent role changes
- Environments with [Active Directory](../integraciones/active-directory.md) integration where AD groups map to Viewtinet roles via [Ad Groups Roles](../integraciones/ad-groups-roles.md)

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
2. In the Available column, check the box next to each [role](roles.md) you want this group to inherit.
3. Click the single-arrow **>** button to move roles to Selected.
4. Click **Save Changes**.

## Membership Behavior

When you add or remove a [user](users.md) from a group, they immediately gain or lose every role assigned to that group — no further edits are needed on their individual user account.

## Groups and External Identity Providers

When using [Active Directory](../integraciones/active-directory.md), AD security groups can be mapped to Viewtinet roles through the [AD Groups & Roles](../integraciones/ad-groups-roles.md) configuration. For [LDAP](../integraciones/ldap-integration.md), a single default role is assigned at login; group-based role mapping is not supported for LDAP.

## Related Pages

- [Roles](roles.md) — Permission sets assigned to groups
- [Users](users.md) — Individual user accounts and group membership
- [Ad Groups Roles](../integraciones/ad-groups-roles.md) — Mapping Active Directory groups to Viewtinet roles
- [Tenants](tenants.md) — Multi-tenancy and data isolation
