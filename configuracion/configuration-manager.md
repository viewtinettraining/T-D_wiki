---
tags: [configuracion, viewtimanager, configuration-manager]
tipo: tecnica
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Configuration Manager

The Configuration Manager in Viewtinet is a comprehensive feature designed to simplify and automate the management of device configurations across your network. It enables administrators to efficiently apply, update, and maintain configurations on multiple devices simultaneously, reducing manual effort and the risk of human error.

The Configuration Manager is accessible via the [[gui-overview|left navigation menu]] when the corresponding license is active. The required permission is `VM_CONFIGURATION_MANAGER_MODULE` (see [[roles]]).

## Core Capabilities

- Apply configuration changes to multiple devices simultaneously
- Schedule recurring or one-off configuration jobs
- Collect and archive device configurations (running-config, startup-config)
- Compare configuration snapshots side-by-side to spot differences
- Merge multiple configuration captures into a single consolidated file

Supported remote access protocols: **SSH** and **Telnet**.

## Prerequisites

Before using the Configuration Manager, the following must be in place in the [[inventory-management|Inventory]]:

1. **Devices added to Inventory** — via [[csv-provisioning|CSV]], [[autodiscovery|Autodiscovery]], or [[manual-provisioning|manual entry]].
2. **Device filter created** — a saved filter in Inventory that selects the target device subset. Filters can use logical operators (AND, OR, NOT) and any device attribute.
3. **Access credentials configured** — SSH and/or Telnet credentials defined in Inventory → Credentials.
4. **Device-credential relations assigned** — in the Inventory Relations tab, mapping devices to their credentials.

Once these prerequisites are met, you can create and run configuration tasks.

## Module Structure

The Configuration Manager has three main sections:

| Section | Purpose | Wiki Page |
|---|---|---|
| Commands | Define reusable command templates to run against devices | [[configuration-commands]] |
| Tasks | Orchestrate recurring or one-off jobs against device groups | [[configuration-tasks]] |
| Configurations | Browse, compare, download, and merge collected config files | [[configuration-manager]] (this page) |

## Configurations Archive

The **Configurations** tab is the central archive for all collected device outputs (typically backups of running-config or startup-config). From here you can:

- **Browse** — use the File Browser to navigate hierarchical folders of `.cfg` files organized by task, subtask, and device.
- **Search / Edit / Delete** — preview files inline, rename them, or remove them from the archive.
- **Download** — select one or more configs and download as a ZIP for offline storage or audit.
- **Compare** — select exactly two files and click **Compare Selected** for a side-by-side diff with highlighted changes.
- **Merge** — select two or more snapshots and click **Merge Selected** to create a unified `.cfg` file.

Use **Compare** before **Merge** to understand every change. Merged files appear with a timestamped name for traceability.

## Related Pages

- [[configuration-commands]] — Command templates and types
- [[configuration-tasks]] — Task scheduling and subtask flow editor
- [[inventory-management]] — Prerequisite inventory setup
- [[roles]] — VM_CONFIGURATION_MANAGER_MODULE permission
- [[viewtimanager-overview]] — Platform overview
