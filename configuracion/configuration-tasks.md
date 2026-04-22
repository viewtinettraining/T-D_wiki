---
title: "Configuration Tasks"
description: "The Tasks tab in the Configuration Manager lets you orchestrate recurring or one-off jobs against groups of devices. A Task is a named schedule plus a device..."
keywords: "configuracion, viewtimanager, configuration-manager, tareas, automatizacion"
---

# Configuration Tasks

The Tasks tab in the [Configuration Manager](configuration-manager.md) lets you orchestrate recurring or one-off jobs against groups of devices. A **Task** is a named schedule plus a device filter; a **Subtask** is a single [command](configuration-commands.md) invocation within that job. Use Tasks to automate backups, compliance checks, or batch configuration pushes on a defined timetable.

## Viewing Existing Tasks

The task list shows:
- **Name** — task identifier
- **Devices Filter** — previously defined filter from [Inventory](inventory-management.md)
- **Cron / Date** — schedule expression or next run timestamp
- **Scheduled** — toggle to enable/disable the cron job
- **Allow Individual Failure** — continue other devices if one fails
- Action icons: Edit, Run, Results, Delete

## Creating a New Task

1. Click **Add a New Task** at the bottom of the list.
2. In the **View Task** dialog, define:
   - **Name** — clear, descriptive title
   - **Filter Devices** — select one of your pre-built [Inventory](autodiscovery.md) device filters
   - **Allow individual failure** — when checked, one device failure does not halt the entire run
   - **Schedule Enabled** — toggle on to access scheduling controls

## Setting the Schedule

Two scheduling modes are available:

- **One-off execution** — toggle on **Next Execution Date** and pick a date/time.
- **Recurring (Cron)** — when Next Execution Date is off and Schedule Enabled is on, configure a cron schedule via the Minutes / Hourly / Daily / Weekly / Monthly tabs.

## Building the Task Flow

After saving the Task properties, the flow editor opens. The Task node appears in purple.

1. **Add a Subtask** — hover over the bottom handle of the Task node and click to spawn a new Subtask node.
2. **Connect** — drag the connector dot from the Task node to the Subtask node.
3. **Configure the Subtask** — click **EDIT** on the Subtask node and fill in:
   - **Name** — descriptive label (e.g., "Get Startup Configs")
   - **Devices** — inherit from the parent Task filter or override with a comma-separated list
   - **Command** — select one of your predefined [Commands](configuration-commands.md)
4. Click **SAVE** in the flow editor.

## Running and Managing Tasks

- **Edit (pencil)** — modify name, filter, or schedule
- **Run (play)** — trigger the task immediately against its device set
- **Delete (trash)** — remove the task entirely
- **Results (clipboard)** — view execution history

## Viewing Task Results

Click **Results** to inspect the history of runs. Each execution shows:
- **Start / Finish** timestamps
- **Hosts Success / Failure** counts
- **Commands Run / Success / Failure** counts

Expand a run to see host-level details, then expand a host to see Subtask Results. Click the eye icon in **Command Output** to view the raw device output (e.g., running-config). Collected configurations are stored in the [Configurations archive](configuration-manager.md).

## Related Pages

- [Configuration Commands](configuration-commands.md) — Command template definitions and types
- [Configuration Manager](configuration-manager.md) — Configurations archive and module overview
- [Inventory Management](inventory-management.md) — Prerequisite device inventory and filters
- [Csv Provisioning](csv-provisioning.md) — One source of inventory device filters
- [Viewtimanager Overview](../productos/viewtimanager-overview.md) — Platform control center
