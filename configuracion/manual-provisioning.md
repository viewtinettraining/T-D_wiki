---
title: "Manual Provisioning"
description: "Manual provisioning is the last resort for onboarding devices into the Inventory when CSV import or Autodiscovery are not feasible — for example, for isolate..."
keywords: "configuracion, viewtimanager, inventario, provisionamiento"
---

# Manual Provisioning

Manual provisioning is the last resort for onboarding devices into the [Inventory](inventory-management.md) when [CSV import](csv-provisioning.md) or [Autodiscovery](autodiscovery.md) are not feasible — for example, for isolated devices or one-off entries. It allows you to add individual devices one at a time.

## Step 1: Open the Devices Overview

1. In the [ViewtiManager](../productos/viewtimanager-overview.md) web console, click **Inventory** in the left menu.
2. Select the **OVERVIEW** tab.
3. Ensure **DEVICES** is active.

## Step 2: Add a New Device Row

Scroll to the bottom of the device list and click **+ ADD NEW DEVICE**. A blank row appears in the table.

## Step 3: Fill in Fields

| Field | Description | Required |
|---|---|---|
| IP / Hostname | Device's IP address or DNS name | Yes |
| oid_group_names | Comma-separated OID group(s) for SNMP polling | Yes |
| sw_version | Software/OS version (e.g., FortiOS 7.10) | No |
| source | Inventory source (e.g., `user_defined`) | No |
| device | Friendly device name | No |
| mac | MAC address | No |
| sys_object_id | SNMP sysObjectID | No |
| system_name | SNMP systemName | No |

## Step 4: Save

Click **SAVE CHANGES**. A confirmation banner confirms the device was added and is now ready for credential assignments and plugin configuration.

## Configuring Credentials After Manual Entry

Credentials define how the system authenticates to collect metrics (SNMP, ICMP) and manage configurations (SSH, Telnet). Supported protocols:
- **ICMP** — basic reachability and latency checks
- **SNMP v1/v2c/v3** — poll counters and device metrics
- **SSH / Telnet** — CLI access for configuration management

Navigate to **Inventory → Credentials**, click **+ ADD NEW CREDENTIAL**, select the protocol, and configure the required parameters (community string for SNMP v1/v2c; Security Level, Auth Protocol, Priv Protocol for SNMPv3).

## Mapping Credentials to Devices (Relations)

After adding credentials, link them to your manually added device:

1. Click **Relations** under the Inventory header.
2. Use the Query Builder to filter to your device (e.g., `dev.ip == '10.10.10.1'`).
3. Select the device row.
4. Scroll to the Credentials panel and select the relevant credentials.
5. Click **SAVE CHANGES**.

## Installing Plugins

The final step is installing one or more Viewtinet [plugins](../conceptos/plugin-architecture.md) to map device data into processing pipelines:

1. Click **PLUGINS** in the Inventory header.
2. Optionally add a filter for your specific device.
3. Expand **network monitoring** and select `snmp_device_config`, `snmp_if_config`, and `icmp`.
4. Click **MODIFY AND INSTALL PLUGINS**, confirm the selections, and click **OK**.
5. Click **FINISH INSTALLATION** in the [V.S. Data Broker](../productos/vs-data-broker-overview.md) console.

## Related Pages

- [Inventory Management](inventory-management.md) — Inventory overview
- [Autodiscovery](autodiscovery.md) — Automatic network scanning alternative
- [Csv Provisioning](csv-provisioning.md) — Bulk CSV import alternative
- [Inventory Maintenance](inventory-maintenance.md) — Ongoing data management
- [Configuration Manager](configuration-manager.md) — Uses inventory devices and credentials
