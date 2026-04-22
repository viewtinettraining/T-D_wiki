---
tags: [configuracion, viewtimanager, admin, roles, rbac]
tipo: tecnica
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Roles

Roles define custom permission sets that control what actions [[users]] and [[groups]] can perform within the Viewtinet platform. Once a role is created, it can be assigned to individual users or to user groups. Roles are managed at **Admin → Roles**.

Roles are also the mechanism used to map [[active-directory|Active Directory]] groups to Viewtinet access levels. See [[ad-groups-roles]] for the mapping procedure.

## Creating a Role

1. In the left sidebar, click **Admin**.
2. Select the **Roles** tab.
3. Click **Add New**.

### Role Details

| Field | Description |
|---|---|
| Name | Unique identifier (e.g., `Network Admin`) |
| Description | Brief summary of the role's purpose |
| Created at | Read-only creation timestamp |
| Updated at | Read-only last-modification timestamp |

## Role Permissions

Use the dual-list interface to grant or revoke granular permissions. Key permissions include:

| Permission | Description |
|---|---|
| `VM_FULL_ACCESS` | Full access to ViewtiManager (excluding R&D) |
| `VS_FULL_ACCESS` | Full access to [[viewtisight-overview|ViewtiSight]] |
| `VS_READ_ONLY` | Read-only access to all ViewtiSight views |
| `VM_ADMIN_MODULE` | Access to ViewtiManager Admin module |
| `VM_INVENTORY_MODULE` | Access to ViewtiManager Inventory module |
| `VM_CONFIGURATION_MANAGER_MODULE` | Access to [[configuration-manager]] |
| `VM_VIEWTIMON_MODULE` | Access to [[viewtimon-overview|ViewtiMon]] module |
| `VM_QOS_MODULE` | Access to ViewtifyQoS module |
| `VM_PLUGINS_MODULE` | Access to V.S. Data Broker |
| `VM_ADMIN_USERS_FILTERED` | Removes Users tab from Admin area |
| `VM_ADMIN_ROLES_FILTERED` | Removes Roles tab from Admin area |
| `VM_ADMIN_TENANTS_FILTERED` | Removes Tenants tab from Admin area |
| `VS_NO_CONTROL_CENTER` | Blocks access to Alarms & Notifications |
| `VS_NO_SCHEDULER` | Denies access to Scheduler |

Permissions follow the pattern **Module_Menu_Tab_Permission**:
- `VM` = ViewtiManager, `VS` = ViewtiSight
- `FILTERED` in the name indicates that access to that area is denied.

## Role Sets (Data Access)

In the **Role Sets** section, determine which database tables ("sets") this role can query. Move items from Allowed Sets to Forbidden Sets to block data access for that role. This provides row/table-level data isolation.

## Role Groups and Role Users

The **Role Groups** panel lists user groups associated with this role (read-only here — manage from [[groups]]). The **Role Users** panel lists individual users with this role (manage from [[users]]).

After updating any section, click **Save Changes** to apply.

## Related Pages

- [[users]] — Assigning roles to individual users
- [[groups]] — Assigning roles to user groups
- [[ad-groups-roles]] — Mapping AD groups to Viewtinet roles
- [[tenants]] — Data access scoping per tenant
