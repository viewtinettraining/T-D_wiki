---
tags: [productos, viewtimanager]
tipo: concepto
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ViewtiManager Overview

ViewtiManager is the main control center for the Viewtinet platform. It provides administrators with a centralized graphical interface to manage configurations, monitor system health, supervise user access, and control all core platform components.

## Role in the Platform

ViewtiManager acts as the administrative hub from which all Viewtinet modules are operated. After authentication via [[login|Viewtiauth]], users land in ViewtiManager and can navigate to any licensed module. It is the single pane of glass for:

- System health monitoring and performance dashboards
- License enforcement and module activation (see [[license-management]])
- User, role, group, and tenant administration (see [[users]], [[roles]], [[groups]], [[tenants]])
- Network device inventory and provisioning (see [[inventory-management]])
- Configuration automation (see [[configuration-manager]])

## Key Modules Accessible from ViewtiManager

The [[gui-overview|GUI sidebar]] exposes the following modules depending on license state:

| Module                | Always Visible | Requires License |     |
| --------------------- | -------------- | ---------------- | --- |
| Home Dashboard        | Yes            | No               |     |
| Viewtisight           | Yes            | No               |     |
| Inventory             | Yes            | No               |     |
| V.S. Data Broker      | Yes            | No               |     |
| Networking            | Yes            | No               |     |
| Admin                 | Yes            | No               |     |
| License               | Yes            | No               |     |
| [[viewtilog-overview  | ViewtiLog]]    | No               | Yes |
| [[viewtimon-overview  | ViewtiMon]]    | No               | Yes |
| [[viewtiqos-overview  | ViewtiQoS]]    | No               | Yes |
| Configuration Manager | No             | Yes              |     |

## Home Dashboard

After login, the Home dashboard provides real-time cluster performance graphs (CPU, memory, network throughput, process counts), disk monitoring metrics (IOPS, latency per partition), and a user login audit panel. These views are selectable from a dropdown within the Home section.

## Integration with Other Viewtinet Components

ViewtiManager controls the lifecycle of companion products. Administrators can start, stop, and restart services for [[viewtisight-overview|ViewtiSight]], [[viewtilog-overview|ViewtiLog]], [[viewtimon-overview|ViewtiMon]], and [[viewtiqos-overview|ViewtiQoS]] from the top bar control buttons. The [[vs-data-broker-overview|V.S. Data Broker]] plugin pipeline is also managed through the Inventory and Plugins views.

## Authentication and Security

All access is routed through the [[viewtiauth|Viewtiauth]] module. Administrators can enforce [[mfa-configuration|multi-factor authentication]], integrate with [[active-directory|Active Directory]], configure [[ldap-integration|LDAP]], and define granular [[roles|role-based access control]].

## System Updates

Platform updates are applied from Admin → Updates (see [[system-updates]]). The process updates the entire platform, including Viewtimanager, ViewtiAuth, ViewtiCore, ViewtiSight, ViewtiMon, ViewtifyQoS, and ViewtiLog in a single operation.
