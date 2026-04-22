---
title: "SSH Extractor"
description: "The SSH Query Connector allows the Visual Smart Data Broker (VSDB) to connect to remote devices using SSH and retrieve system metrics or execute custom comma..."
keywords: "integracion, ssh, extractor, vs-data-broker"
---

# SSH Extractor

The **SSH Query Connector** allows the [Visual Smart Data Broker (VSDB)](../productos/vs-data-broker-overview.md) to connect to remote devices using SSH and retrieve system metrics or execute custom commands. It is especially useful for monitoring servers or network devices where [SNMP](snmp-extractor.md) or other protocols are not enabled but SSH access is available.

## Key Features

- Establishes SSH sessions with target hosts
- Collects standard system metrics: CPU, memory, disk, network interfaces, uptime
- Supports execution of custom commands defined by the user
- Password-based authentication supported (other SSH methods may be available)
- Scheduled connector — runs periodically based on the configured execution frequency

## Configuration Parameters

| Parameter | Description |
|---|---|
| **Connector Type** | SSH Query Connector |
| **Pipeline Name** | Unique name (e.g., `my_ssh_connector`) |
| **Frequency Type** | `Scheduled` (cron) or `Periodic` |
| **Cron Expression** | Execution schedule (e.g., every minute) |
| **Number of Executions** | `-1` for unlimited |
| **Host Name** | IP address or hostname of the target device |
| **Port** | Default SSH port is `22` |
| **User** | SSH username |
| **Authentication Type** | Password or other supported method |
| **Password** | Corresponding credential |

## Available Query Types

| Query | Data Retrieved |
|---|---|
| `cpu` | CPU usage percentage |
| `disk` | Disk utilization |
| `memory` | Memory usage |
| `network` | Network interface metrics |
| `service` | Service status |
| `uname` | System information |
| `uptime` | System uptime |
| `cmd` | Custom command output |

## Security Note

Use restricted, read-only accounts rather than root for production environments. Ensure credentials have only the permissions necessary to execute the selected query types.

## Related Pages

- [Etl Pipeline](../conceptos/etl-pipeline.md) — ETL pipeline context
- [Snmp Extractor](snmp-extractor.md) — Alternative polling connector for SNMP-capable devices
- [Wmi Extractor](wmi-extractor.md) — Windows alternative (deprecated)
- [Windows Remote Management](windows-remote-management.md) — Preferred Windows monitoring alternative
- [Plugin Categories](../conceptos/plugin-categories.md) — SSH is a dedicated category in VSDB
