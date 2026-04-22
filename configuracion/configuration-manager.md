---
title: "Configuration Manager"
description: "The Configuration Manager in Viewtinet is a comprehensive feature designed to simplify and automate the management of device configurations across your netwo..."
keywords: "configuracion, viewtimanager, configuration-manager"
---

# Configuration Manager

The Configuration Manager in Viewtinet is a comprehensive feature designed to simplify and automate the management of device configurations across your network. It enables administrators to efficiently apply, update, and maintain configurations on multiple devices simultaneously, reducing manual effort and the risk of human error.

The Configuration Manager is accessible via the [left navigation menu](gui-overview.md) when the corresponding license is active. The required permission is `VM_CONFIGURATION_MANAGER_MODULE` (see [Roles](roles.md)).

## Core Capabilities

- Apply configuration changes to multiple devices simultaneously
- Schedule recurring or one-off configuration jobs
- Collect and archive device configurations (running-config, startup-config)
- Compare configuration snapshots side-by-side to spot differences
- Merge multiple configuration captures into a single consolidated file

Supported remote access protocols: **SSH** and **Telnet**.

## Prerequisites

Before using the Configuration Manager, the following must be in place in the [Inventory](inventory-management.md):

1. **Devices added to Inventory** — via [CSV](csv-provisioning.md), [Autodiscovery](autodiscovery.md), or [manual entry](manual-provisioning.md).
2. **Device filter created** — a saved filter in Inventory that selects the target device subset. Filters can use logical operators (AND, OR, NOT) and any device attribute.
3. **Access credentials configured** — SSH and/or Telnet credentials defined in Inventory → Credentials.
4. **Device-credential relations assigned** — in the Inventory Relations tab, mapping devices to their credentials.

Once these prerequisites are met, you can create and run configuration tasks.

## Module Structure

The Configuration Manager has three main sections:

| Section | Purpose | Wiki Page |
|---|---|---|
| Commands | Define reusable command templates to run against devices | [Configuration Commands](configuration-commands.md) |
| Tasks | Orchestrate recurring or one-off jobs against device groups | [Configuration Tasks](configuration-tasks.md) |
| Configurations | Browse, compare, download, and merge collected config files | [Configuration Manager](configuration-manager.md) (this page) |

## Configurations Archive

The **Configurations** tab is the central archive for all collected device outputs (typically backups of running-config or startup-config). From here you can:

- **Browse** — use the File Browser to navigate hierarchical folders of `.cfg` files organized by task, subtask, and device.
- **Search / Edit / Delete** — preview files inline, rename them, or remove them from the archive.
- **Download** — select one or more configs and download as a ZIP for offline storage or audit.
- **Compare** — select exactly two files and click **Compare Selected** for a side-by-side diff with highlighted changes.
- **Merge** — select two or more snapshots and click **Merge Selected** to create a unified `.cfg` file.

Use **Compare** before **Merge** to understand every change. Merged files appear with a timestamped name for traceability.

## Related Pages

- [Configuration Commands](configuration-commands.md) — Command templates and types
- [Configuration Tasks](configuration-tasks.md) — Task scheduling and subtask flow editor
- [Inventory Management](inventory-management.md) — Prerequisite inventory setup
- [Roles](roles.md) — VM_CONFIGURATION_MANAGER_MODULE permission
- [Viewtimanager Overview](../productos/viewtimanager-overview.md) — Platform overview
