---
tags: [configuracion, viewtimanager, gui]
tipo: tecnica
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# GUI Overview

The ViewtiManager graphical user interface is divided into three main zones: the top bar, the left sidebar navigation menu, and the main content panel. Together they provide centralized access to all [[viewtimanager-overview|ViewtiManager]] modules and system controls.

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
| Admin | Manage [[users]], [[roles]], [[groups]], [[tenants]], and auth |
| License | Apply and monitor platform [[license-management|licenses]] |

The following items appear **only when the corresponding feature is licensed**:

| Menu Item | Description |
|---|---|
| [[viewtilog-overview|ViewtiLog]] | Log ingestion module monitoring and configuration |
| [[viewtimon-overview|ViewtiMon]] | Deep traffic monitoring module |
| [[viewtiqos-overview|ViewtiQoS]] | QoS policy engine with bypass controls |
| Configuration Manager | Import, export, and replicate configuration templates |

## Main Content Panel

The central panel renders the content for the selected module. Common panel elements include:

- **STATUS tab** — live system metrics and health indicators (Running, Issues)
- **CONFIGURATION tab** — modify service parameters
- **HOSTS LIST tab** — view or assign cluster nodes
- **ISSUES tab** — alerts and configuration errors
- Additional tabs such as SIGNATURES or BUSINESS GROUPS may appear in modules like ViewtiMon or ViewtifyQoS

## Navigation Flow

After [[login|authenticating via Viewtiauth]], users see an App Selector that routes them to either ViewtiManager or [[viewtisight-overview|ViewtiSight]] depending on their assigned [[roles|role permissions]]. Once inside ViewtiManager, the sidebar allows navigation between all modules without re-authentication.

For licensing-related display changes, see [[license-management]].
