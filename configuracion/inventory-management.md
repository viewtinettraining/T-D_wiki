---
tags: [configuracion, viewtimanager, inventario]
tipo: concepto
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
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
| Autodiscovery | Dynamically scans network ranges; discovers and imports devices automatically | [[autodiscovery]] |
| CSV Import | Bulk onboarding from a structured CSV file | [[csv-provisioning]] |
| Manual Entry | One device at a time; last resort for isolated or one-off devices | [[manual-provisioning]] |

## Inventory Tabs

The Inventory section in [[viewtimanager-overview|ViewtiManager]] is organized into tabs:

- **Overview / Devices** — main device table with filtering and column management
- **Credentials** — protocol-specific authentication entries (SNMP, ICMP, SSH, Telnet)
- **Relations** — device-to-credential mapping
- **Plugins** — assign monitoring plugins (e.g., Network Monitoring) to device groups
- **Autodiscovery** — launch and review network scan jobs

## Integration with Configuration Manager

The Inventory is also a prerequisite for the [[configuration-manager]]. Devices must exist in inventory with proper credentials and device-credential relations before configuration tasks can be executed against them.

## Maintenance

The [[inventory-maintenance]] page covers column management, custom column creation, merging duplicate rows, deleting records, CSV export, and pipeline/plugin lookup.

## Related Pages

- [[autodiscovery]] — Automatic device discovery
- [[csv-provisioning]] — Bulk CSV import
- [[manual-provisioning]] — Manual device entry
- [[inventory-maintenance]] — Maintenance tasks and data hygiene
- [[configuration-manager]] — Configuration Manager (requires inventory setup)
- [[plugin-architecture]] — Plugin framework used in Inventory Plugins tab
