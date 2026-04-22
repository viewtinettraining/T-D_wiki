---
title: "Inventory Management"
description: "The Inventory feature in Viewtinet provides a unified, authoritative repository of all network assets and their key properties. Rather than scattering device..."
keywords: "configuracion, viewtimanager, inventario"
---

# Inventory Management

The Inventory feature in Viewtinet provides a unified, authoritative repository of all network assets and their key properties. Rather than scattering device details across multiple tools, Inventory centralizes device records, credentials, relationship mapping, and discovery integration into a single platform.

This feature is available starting from **Viewtinet v6.3.5 build 2353** (released November 11, 2024).

## What Inventory Manages

- **Device Records** — every managed endpoint (routers, switches, servers, VMs) is stored as a structured entry with IP/hostname, vendor, model, OS, firmware version, and custom tags.
- **Credential Management** — SNMP community strings, SSH keys, WMI/WinRM, Telnet, ICMP, and other access credentials are maintained in the same system.
- **Relationship Mapping** — links each device to the specific data-collection protocols and sources used to acquire performance counters and metrics.
- **Discovery Integration** — records the output of automated discovery jobs (SNMP walks, port scans, OS detection, DNS lookups).

## Provisioning Methods

Devices can be added to the inventory in three ways:

| Method | Description | Wiki Page |
|---|---|---|
| Autodiscovery | Dynamically scans network ranges; discovers and imports devices automatically | [Autodiscovery](autodiscovery.md) |
| CSV Import | Bulk onboarding from a structured CSV file | [Csv Provisioning](csv-provisioning.md) |
| Manual Entry | One device at a time; last resort for isolated or one-off devices | [Manual Provisioning](manual-provisioning.md) |

## Inventory Tabs

The Inventory section in [ViewtiManager](../productos/viewtimanager-overview.md) is organized into tabs:

- **Overview / Devices** — main device table with filtering and column management
- **Credentials** — protocol-specific authentication entries (SNMP, ICMP, SSH, Telnet)
- **Relations** — device-to-credential mapping
- **Plugins** — assign monitoring plugins (e.g., Network Monitoring) to device groups
- **Autodiscovery** — launch and review network scan jobs

## Integration with Configuration Manager

The Inventory is also a prerequisite for the [Configuration Manager](configuration-manager.md). Devices must exist in inventory with proper credentials and device-credential relations before configuration tasks can be executed against them.

## Maintenance

The [Inventory Maintenance](inventory-maintenance.md) page covers column management, custom column creation, merging duplicate rows, deleting records, CSV export, and pipeline/plugin lookup.

## Related Pages

- [Autodiscovery](autodiscovery.md) — Automatic device discovery
- [Csv Provisioning](csv-provisioning.md) — Bulk CSV import
- [Manual Provisioning](manual-provisioning.md) — Manual device entry
- [Inventory Maintenance](inventory-maintenance.md) — Maintenance tasks and data hygiene
- [Configuration Manager](configuration-manager.md) — Configuration Manager (requires inventory setup)
- [Plugin Architecture](../conceptos/plugin-architecture.md) — Plugin framework used in Inventory Plugins tab
