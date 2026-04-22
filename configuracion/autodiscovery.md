---
title: "Autodiscovery"
description: "Autodiscovery allows ViewtiManager to dynamically scan network ranges and automatically onboard devices into the Inventory — no CSV file required. Unlike CSV..."
keywords: "configuracion, viewtimanager, inventario, autodiscovery"
---

# Autodiscovery

Autodiscovery allows ViewtiManager to dynamically scan network ranges and automatically onboard devices into the [Inventory](inventory-management.md) — no CSV file required. Unlike [CSV import](csv-provisioning.md), Autodiscovery discovers unknown devices on the fly, gathers live SNMP/ICMP data during the scan, and auto-populates inventory fields such as MAC address, sysObjectID, and systemName.

## Launch Autodiscovery

1. In the [ViewtiManager](../productos/viewtimanager-overview.md) web console, click **Inventory → AUTODISCOVERY**.
2. Click **LAUNCH NEW AUTO DISCOVERY**.

## Specify Targets

Enter one or more nmap-compatible target specifications in the **Targets** field. Supported formats:

- **Single IP**: `10.30.23.41`
- **Range of IPs**: `10.30.23.41-50`
- **CIDR block**: `10.30.23.0/24`
- **Comma-separated list**: `10.30.23.41,10.30.23.42`
- **Hostname or DNS name**: `router1.example.com`

Also fill in **Pipeline Name**, **Depth**, **Execute Timeout**, and **Community string**, then click **RUN**.

## Review and Pre-Process Results

Once the scan completes:

1. Select the execution ID in the left pane.
2. Switch to the **DEVICES** tab under Autodiscovery.
3. Review the discovered hosts table (IP/Hostname, MAC, sw_version, sys_object_id, system_name).
4. Use the filter box or Query Builder to include or exclude devices before import.

## Import into Inventory

1. Tick the checkboxes for devices to onboard (or use the header checkbox for all).
2. Click **IMPORT INTO INVENTORY** at the top right.
3. Selected hosts are added to the main Inventory view.
4. Switch to the **OVERVIEW** tab under Inventory to see the newly imported hosts.

## Post-Import Steps

After importing, you typically need to:

1. **Assign OID Groups** — add the `oid_group_names` column and assign SNMP OID group names to devices.
2. **Configure Credentials** — set up ICMP, SNMP (v1/v2c/v3), SSH, or Telnet credentials in the Credentials tab.
3. **Map Relations** — link devices to their credentials in the Relations tab.
4. **Install Plugins** — assign monitoring plugins (e.g., Network Monitoring with `snmp_device_config`, `snmp_if_config`, `icmp`) from the Plugins tab.

If SNMP credentials were imported during Autodiscovery, only ICMP credentials need to be created manually.

## Inventory Filtering

Autodiscovery results and the main Inventory view both support a Query Builder for filtering by any device attribute. Conditions can be combined with AND/OR logic, saved for later reuse, and applied to bulk operations.

## Related Pages

- [Inventory Management](inventory-management.md) — Inventory overview and tab structure
- [Csv Provisioning](csv-provisioning.md) — Alternative bulk provisioning via CSV
- [Manual Provisioning](manual-provisioning.md) — Manual one-by-one device entry
- [Inventory Maintenance](inventory-maintenance.md) — Column management and data hygiene
- [Plugin Architecture](../conceptos/plugin-architecture.md) — Plugin framework underlying the Plugins tab
- [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) — Data routing after plugin installation
