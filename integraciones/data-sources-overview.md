---
title: "Data Sources Overview"
description: "The VS Data Broker supports a wide range of data source types through its Extract stage connectors. Each connector is designed for a specific protocol, data ..."
keywords: "integraciones, vsdb, extractor"
---

# Data Sources Overview

The [VS Data Broker](../productos/vs-data-broker-overview.md) supports a wide range of data source types through its Extract stage connectors. Each connector is designed for a specific protocol, data format, or integration pattern. Connectors are assembled into [custom plugins](../conceptos/customized-plugin.md) following the [Plugin Architecture](../conceptos/plugin-architecture.md) and [Plugin Template](../conceptos/plugin-template.md).

This page provides a reference overview of all supported data source categories and the connectors available in each.

## Network Flow and Traffic

These connectors capture network traffic at the packet or flow level.

| Connector | Description |
|---|---|
| [Ethernet Streamer](ethernet-streamer.md) | Continuous listener that captures raw binary traffic (Syslog, NetFlow, sFlow) to disk. Does not parse — acts as a capture layer for downstream connectors. |
| [Netflow Extractor](netflow-extractor.md) | Decodes NetFlow, jFlow, and NetStream records from binary dumps or direct UDP streams. |
| [Sflow Extractor](sflow-extractor.md) | Decodes sFlow datagrams for interface-level traffic sampling. |
| [Flow Emitter](flow-emitter.md) | Internal connector exposing DPI-enriched per-flow data from the [Viewtimon](../productos/viewtimon-overview.md) engine. |

## Logs and Events

| Connector | Description |
|---|---|
| [Syslog Extractor](syslog-extractor.md) | Parses Syslog messages from binary captures or direct UDP/TCP input. |
| [Snmp Trap Connector](snmp-trap-connector.md) | Receives and processes SNMP trap notifications from network devices. |

## Active Polling (SNMP, ICMP, WMI)

These connectors actively query devices at configured intervals.

| Connector | Description |
|---|---|
| [Snmp Extractor](snmp-extractor.md) | Polls SNMP OIDs from network devices and servers using SNMP v1/v2c/v3. |
| [Icmp Extractor](icmp-extractor.md) | Sends ICMP probes to measure reachability and round-trip times. |
| [Wmi Extractor](wmi-extractor.md) | Queries Windows Management Instrumentation on Windows hosts. |
| [Windows Remote Management](windows-remote-management.md) | Executes remote commands on Windows hosts via WinRM. |

## Remote Shell and SSH

| Connector | Description |
|---|---|
| [Ssh Extractor](ssh-extractor.md) | Connects to Linux/Unix devices via SSH and executes commands to retrieve structured output. |
| [Command Executor](command-executor.md) | Runs arbitrary shell commands or bash scripts locally on the Viewtilog host. |

## File and Directory Based

| Connector | Description |
|---|---|
| [Csv Extractor](csv-extractor.md) | Reads structured CSV files from local directories or remote sources. |
| [File List Extractor](file-list-extractor.md) | Monitors a directory for new files, moves them for processing, and prepares them for SCP delivery. |

## Database

| Connector | Description |
|---|---|
| [Mongodb Extractor](mongodb-extractor.md) | Queries MongoDB collections and ingests documents into the ETL pipeline. |

## Script and Custom Logic

| Connector | Description |
|---|---|
| [Python Task Extractor](python-task-extractor.md) | Executes Python scripts as data sources, allowing fully custom extraction logic. |
| [Command Executor](command-executor.md) | General-purpose shell command execution with CSV-compatible output parsing. |

## Directory Services

These are authentication integrations rather than data extractors, but they serve as identity data sources.

| Integration | Description |
|---|---|
| [Active Directory](active-directory.md) | Authenticates users via AD and supports group-to-role mapping through [Ad Groups Roles](ad-groups-roles.md). |
| [Ldap Integration](ldap-integration.md) | Authenticates users via an external LDAP directory with single default role assignment. |

## Choosing a Connector

When designing a data collection plugin, consider:

1. **Protocol**: does the source speak SNMP, Syslog, NetFlow, HTTP, or proprietary CLI?
2. **Push vs. Pull**: does the device send data (Syslog, NetFlow, traps) or must you query it (SNMP, SSH, WMI)?
3. **Continuous vs. Scheduled**: flow and log sources benefit from [Ethernet Streamer](ethernet-streamer.md) continuous capture; metrics polling uses periodic or cron-based connectors.
4. **Output format**: ensure connector output is parseable — CSV-like for most connectors, binary for [Ethernet Streamer](ethernet-streamer.md).

For the Load stage destinations available after extraction and transformation, see [Data Producers](data-producers.md). For the Transform step between Extract and Load, see [Column Constant Adder](column-constant-adder.md) and the broader [Etl Pipeline](../conceptos/etl-pipeline.md) documentation.
