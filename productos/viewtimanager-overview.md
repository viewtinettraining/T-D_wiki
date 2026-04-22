---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'ViewtiManager Overview'
id: E7U-VMY-USN-LXH
slug: viewtimanager-overview
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# ViewtiManager Overview

ViewtiManager is the main control center for the Viewtinet platform. It provides administrators with a centralized graphical interface to manage configurations, monitor system health, supervise user access, and control all core platform components.

## Role in the Platform

ViewtiManager acts as the administrative hub from which all Viewtinet modules are operated. After authentication via [Viewtiauth](../configuracion/login.md), users land in ViewtiManager and can navigate to any licensed module. It is the single pane of glass for:

- System health monitoring and performance dashboards
- License enforcement and module activation (see [License Management](../configuracion/license-management.md))
- User, role, group, and tenant administration (see [Users](../configuracion/users.md), [Roles](../configuracion/roles.md), [Groups](../configuracion/groups.md), [Tenants](../configuracion/tenants.md))
- Network device inventory and provisioning (see [Inventory Management](../configuracion/inventory-management.md))
- Configuration automation (see [Configuration Manager](../configuracion/configuration-manager.md))

## Key Modules Accessible from ViewtiManager

The [GUI sidebar](../configuracion/gui-overview.md) exposes the following modules depending on license state:

| Module                | Always Visible | Requires License |     |
| --------------------- | -------------- | ---------------- | --- |
| Home Dashboard        | Yes            | No               |     |
| Viewtisight           | Yes            | No               |     |
| Inventory             | Yes            | No               |     |
| V.S. Data Broker      | Yes            | No               |     |
| Networking            | Yes            | No               |     |
| Admin                 | Yes            | No               |     |
| License               | Yes            | No               |     |
| [ViewtiLog](viewtilog-overview.md)    | No               | Yes |
| [ViewtiMon](viewtimon-overview.md)    | No               | Yes |
| [ViewtiQoS](viewtiqos-overview.md)    | No               | Yes |
| Configuration Manager | No             | Yes              |     |

## Home Dashboard

After login, the Home dashboard provides real-time cluster performance graphs (CPU, memory, network throughput, process counts), disk monitoring metrics (IOPS, latency per partition), and a user login audit panel. These views are selectable from a dropdown within the Home section.

## Integration with Other Viewtinet Components

ViewtiManager controls the lifecycle of companion products. Administrators can start, stop, and restart services for [ViewtiSight](viewtisight-overview.md), [ViewtiLog](viewtilog-overview.md), [ViewtiMon](viewtimon-overview.md), and [ViewtiQoS](viewtiqos-overview.md) from the top bar control buttons. The [V.S. Data Broker](vs-data-broker-overview.md) plugin pipeline is also managed through the Inventory and Plugins views.

## Authentication and Security

All access is routed through the [Viewtiauth](../integraciones/viewtiauth.md) module. Administrators can enforce [multi-factor authentication](../integraciones/mfa-configuration.md), integrate with [Active Directory](../integraciones/active-directory.md), configure [LDAP](../integraciones/ldap-integration.md), and define granular [role-based access control](../configuracion/roles.md).

## System Updates

Platform updates are applied from Admin → Updates (see [System Updates](../configuracion/system-updates.md)). The process updates the entire platform, including Viewtimanager, ViewtiAuth, ViewtiCore, ViewtiSight, ViewtiMon, ViewtifyQoS, and ViewtiLog in a single operation.
