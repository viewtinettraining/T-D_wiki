---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'CSV Provisioning'
id: MAY-JGX-X03-NWR
slug: csv-provisioning
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# CSV Provisioning

Viewtinet supports bulk onboarding of devices into the [Inventory](inventory-management.md) through a simple CSV import. This method is preferred over [manual entry](manual-provisioning.md) when adding multiple devices at once, and complements [Autodiscovery](autodiscovery.md) for environments where target IPs are already known.

## CSV File Requirements

| Rule | Detail |
|---|---|
| Mandatory field | `ip_address` or `hostname` — at least one must be present in every row |
| Delimiter | Comma (`,`) as the field separator; quoted strings are supported |
| Header row | First line must contain column names |
| Encoding | UTF-8 without BOM recommended |
| File size | For inventories >10,000 rows, split into files of no more than 5,000 rows each |

## Recommended Optional Fields

Adding extra columns improves filtering and grouping capabilities:

- `location` (e.g., "Data Center 1", "Building A")
- `device_type` (e.g., "router", "switch", "firewall")
- `vendor` (e.g., "Cisco", "Juniper")
- `model` (e.g., "ISR4451", "EX4300")
- `os_version` (e.g., "IOS XE 17.3.1")
- `department` (e.g., "IT", "Engineering")

## Example CSV

```csv
ip,device,vendor,operating_system,sw_version
192.168.1.101,training,LINUX,Ubuntu 22.04,PROXMOX 8.1.4
10.30.23.1,cancerbero,LINUX,Free BSD,PFSense 2.7.2
10.30.23.8,perseo,MICROSOFT,Windows Server,2022
```

## CSV Import Procedure

1. In the [ViewtiManager](../productos/viewtimanager-overview.md) web console, click **Inventory** in the left-hand menu.
2. Click **IMPORT A LIST OF DEVICES AND/OR CREDENTIALS FROM CSV** at the top of the Devices tab.
3. In the file chooser dialog, locate and select your CSV file, then click **Open**.
4. In the preview dialog, verify the **Separator** (`,` by default) and **Source name**.
5. Click **AUTO-ASSIGN COLUMNS** to map CSV headers to Viewtinet inventory fields (`dev.ip`, `dev.hostname`, etc.).
6. Once all required fields are mapped, click **IMPORT FIELDS**.
7. After import completes, click **SAVE** at the bottom right to finalize adding the devices.

Upon completion, Viewtinet displays a summary of imported devices and any rows that failed validation.

## Post-Import Steps

After importing devices via CSV, you typically need to:

1. Assign **OID Groups** (`oid_group_names`) to device rows for SNMP polling.
2. Configure **Credentials** (SNMP, ICMP, SSH, Telnet) in the Credentials tab.
3. Map **Relations** between devices and credentials.
4. Install **Plugins** (e.g., Network Monitoring) in the Plugins tab.

These steps are shared with [Autodiscovery](autodiscovery.md) and [Manual Provisioning](manual-provisioning.md).

## Filtering After Import

The Inventory Query Builder lets you narrow the device list by any attribute (IP, vendor, OS version, etc.), combine conditions with AND/OR logic, and save filters for reuse. Saved filters are also used by the [Configuration Manager](configuration-manager.md) for targeting devices in configuration tasks.

## Related Pages

- [Inventory Management](inventory-management.md) — Inventory overview
- [Autodiscovery](autodiscovery.md) — Automatic discovery alternative
- [Manual Provisioning](manual-provisioning.md) — One-by-one device entry
- [Inventory Maintenance](inventory-maintenance.md) — Column management and data hygiene
- [Configuration Manager](configuration-manager.md) — Uses inventory devices for config tasks
