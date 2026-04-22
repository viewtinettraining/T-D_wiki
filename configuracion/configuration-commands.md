---
title: "Configuration Commands"
description: "The Commands pane of the Configuration Manager is where you view, manage, and execute reusable command templates against your network devices. Commands are t..."
keywords: "configuracion, viewtimanager, configuration-manager, comandos"
---

# Configuration Commands

The Commands pane of the [Configuration Manager](configuration-manager.md) is where you view, manage, and execute reusable command templates against your network devices. Commands are the building blocks used by [Tasks](configuration-tasks.md) to perform configuration and data collection operations.

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
- **Collect Config** automatically retrieves the device's running or startup configuration after the command executes, storing it in the [Configurations archive](configuration-manager.md).

## Usage in Tasks

Commands are referenced by [Task subtasks](configuration-tasks.md). A Task defines the schedule and device filter; each Subtask within the Task calls one Command. This modular design allows the same command to be reused across different tasks and device groups.

## Prerequisites

Commands execute against devices defined in the [Inventory](inventory-management.md) with proper [credentials](manual-provisioning.md) configured and [device-credential relations](configuration-manager.md) established.

## Related Pages

- [Configuration Tasks](configuration-tasks.md) — Task scheduling, subtask flow, and execution results
- [Configuration Manager](configuration-manager.md) — Configurations archive and module overview
- [Inventory Management](inventory-management.md) — Inventory prerequisite setup
- [Viewtimanager Overview](../productos/viewtimanager-overview.md) — Platform control center
