---
title: "GUI Overview"
description: "The ViewtiManager graphical user interface is divided into three main zones: the top bar, the left sidebar navigation menu, and the main content panel. Toget..."
keywords: "configuracion, viewtimanager, gui"
---

# GUI Overview

The ViewtiManager graphical user interface is divided into three main zones: the top bar, the left sidebar navigation menu, and the main content panel. Together they provide centralized access to all [ViewtiManager](../productos/viewtimanager-overview.md) modules and system controls.

## Top Bar

Located in the upper-right corner of the interface, the top bar displays:

- **User Info** — shows the currently logged-in user (e.g., `Logged in as admin`).
- **Module Info** — shows the selected module name and version, uptime, and a link to release notes.
- **Control Buttons** — for licensed modules, `START`, `STOP`, and `RESTART` buttons appear for service management.

## Left Navigation Menu (Sidebar)

The vertical sidebar lists all accessible modules. The following items are always visible regardless of license state:

| Menu Item | Description |
|---|---|
| Home | General status and cluster performance overview |
| Viewtisight | Visualization and dashboard service control |
| Inventory | Register and manage devices and data sources |
| V.S. Data Broker | Configure data routing and telemetry transport |
| Networking | IP addresses, DNS, routing, and interface settings |
| Admin | Manage [Users](users.md), [Roles](roles.md), [Groups](groups.md), [Tenants](tenants.md), and auth |
| License | Apply and monitor platform [licenses](license-management.md) |

The following items appear **only when the corresponding feature is licensed**:

| Menu Item | Description |
|---|---|
| [ViewtiLog](../productos/viewtilog-overview.md) | Log ingestion module monitoring and configuration |
| [ViewtiMon](../productos/viewtimon-overview.md) | Deep traffic monitoring module |
| [ViewtiQoS](../productos/viewtiqos-overview.md) | QoS policy engine with bypass controls |
| Configuration Manager | Import, export, and replicate configuration templates |

## Main Content Panel

The central panel renders the content for the selected module. Common panel elements include:

- **STATUS tab** — live system metrics and health indicators (Running, Issues)
- **CONFIGURATION tab** — modify service parameters
- **HOSTS LIST tab** — view or assign cluster nodes
- **ISSUES tab** — alerts and configuration errors
- Additional tabs such as SIGNATURES or BUSINESS GROUPS may appear in modules like ViewtiMon or ViewtifyQoS

## Navigation Flow

After [authenticating via Viewtiauth](login.md), users see an App Selector that routes them to either ViewtiManager or [ViewtiSight](../productos/viewtisight-overview.md) depending on their assigned [role permissions](roles.md). Once inside ViewtiManager, the sidebar allows navigation between all modules without re-authentication.

For licensing-related display changes, see [License Management](license-management.md).
