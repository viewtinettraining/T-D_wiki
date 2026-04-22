---
tags: [configuracion, viewtimanager, configuration-manager, comandos]
tipo: tecnica
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Configuration Commands

The Commands pane of the [[configuration-manager|Configuration Manager]] is where you view, manage, and execute reusable command templates against your network devices. Commands are the building blocks used by [[configuration-tasks|Tasks]] to perform configuration and data collection operations.

## Overview

The Commands list shows all existing command templates with options to search, execute, or delete them. You can run any existing command directly against one or more devices, or create a new command template.

## Creating a Command

Click **Add a New Command** and supply the following fields:

| Field | Description |
|---|---|
| Name | A descriptive label for easy identification |
| Command | The actual text to send to the device |
| Type | How the command payload is structured (see types below) |
| Require Config | If checked, this command only runs against devices that already have an existing config |
| Collect Config | If checked, the device's configuration is automatically fetched after execution |

## Command Types

| Type | Description |
|---|---|
| **Commands List** | A semicolon-separated list of one-off operational commands (e.g., `show version; show interfaces`). Use for general, non-configuration queries. |
| **Config Set** | A semicolon-separated list of configuration commands to apply in sequence (e.g., `interface GigabitEthernet0/1; description Uplink`). Do not include the command to enter configuration mode. |
| **Config File** | Upload a file containing the full set of configuration commands. Best for large pre-built templates or backups to push wholesale. |
| **Commands Prompt List** | A list of `{command ↔ expected-prompt}` pairs for advanced interactive sessions. Use when navigating complex multi-stage dialogues or custom device prompts. |

## Execution Behavior

- **Require Config** ensures safety by limiting execution to devices that already have a known configuration baseline. This prevents commands that depend on an existing config from running against unconfigured devices.
- **Collect Config** automatically retrieves the device's running or startup configuration after the command executes, storing it in the [[configuration-manager|Configurations archive]].

## Usage in Tasks

Commands are referenced by [[configuration-tasks|Task subtasks]]. A Task defines the schedule and device filter; each Subtask within the Task calls one Command. This modular design allows the same command to be reused across different tasks and device groups.

## Prerequisites

Commands execute against devices defined in the [[inventory-management|Inventory]] with proper [[manual-provisioning|credentials]] configured and [[configuration-manager|device-credential relations]] established.

## Related Pages

- [[configuration-tasks]] — Task scheduling, subtask flow, and execution results
- [[configuration-manager]] — Configurations archive and module overview
- [[inventory-management]] — Inventory prerequisite setup
- [[viewtimanager-overview]] — Platform control center
