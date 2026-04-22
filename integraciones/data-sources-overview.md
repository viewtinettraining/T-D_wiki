---
tags: [integraciones, vsdb, extractor]
tipo: concepto
fuentes: ["vs-data-broker-overview"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Data Sources Overview

The [[vs-data-broker-overview|VS Data Broker]] supports a wide range of data source types through its Extract stage connectors. Each connector is designed for a specific protocol, data format, or integration pattern. Connectors are assembled into [[customized-plugin|custom plugins]] following the [[plugin-architecture]] and [[plugin-template]].

This page provides a reference overview of all supported data source categories and the connectors available in each.

## Network Flow and Traffic

These connectors capture network traffic at the packet or flow level.

| Connector | Description |
|---|---|
| [[ethernet-streamer]] | Continuous listener that captures raw binary traffic (Syslog, NetFlow, sFlow) to disk. Does not parse — acts as a capture layer for downstream connectors. |
| [[netflow-extractor]] | Decodes NetFlow, jFlow, and NetStream records from binary dumps or direct UDP streams. |
| [[sflow-extractor]] | Decodes sFlow datagrams for interface-level traffic sampling. |
| [[flow-emitter]] | Internal connector exposing DPI-enriched per-flow data from the [[viewtimon-overview|Viewtimon]] engine. |

## Logs and Events

| Connector | Description |
|---|---|
| [[syslog-extractor]] | Parses Syslog messages from binary captures or direct UDP/TCP input. |
| [[snmp-trap-connector]] | Receives and processes SNMP trap notifications from network devices. |

## Active Polling (SNMP, ICMP, WMI)

These connectors actively query devices at configured intervals.

| Connector | Description |
|---|---|
| [[snmp-extractor]] | Polls SNMP OIDs from network devices and servers using SNMP v1/v2c/v3. |
| [[icmp-extractor]] | Sends ICMP probes to measure reachability and round-trip times. |
| [[wmi-extractor]] | Queries Windows Management Instrumentation on Windows hosts. |
| [[windows-remote-management]] | Executes remote commands on Windows hosts via WinRM. |

## Remote Shell and SSH

| Connector | Description |
|---|---|
| [[ssh-extractor]] | Connects to Linux/Unix devices via SSH and executes commands to retrieve structured output. |
| [[command-executor]] | Runs arbitrary shell commands or bash scripts locally on the Viewtilog host. |

## File and Directory Based

| Connector | Description |
|---|---|
| [[csv-extractor]] | Reads structured CSV files from local directories or remote sources. |
| [[file-list-extractor]] | Monitors a directory for new files, moves them for processing, and prepares them for SCP delivery. |

## Database

| Connector | Description |
|---|---|
| [[mongodb-extractor]] | Queries MongoDB collections and ingests documents into the ETL pipeline. |

## Script and Custom Logic

| Connector | Description |
|---|---|
| [[python-task-extractor]] | Executes Python scripts as data sources, allowing fully custom extraction logic. |
| [[command-executor]] | General-purpose shell command execution with CSV-compatible output parsing. |

## Directory Services

These are authentication integrations rather than data extractors, but they serve as identity data sources.

| Integration | Description |
|---|---|
| [[active-directory]] | Authenticates users via AD and supports group-to-role mapping through [[ad-groups-roles]]. |
| [[ldap-integration]] | Authenticates users via an external LDAP directory with single default role assignment. |

## Choosing a Connector

When designing a data collection plugin, consider:

1. **Protocol**: does the source speak SNMP, Syslog, NetFlow, HTTP, or proprietary CLI?
2. **Push vs. Pull**: does the device send data (Syslog, NetFlow, traps) or must you query it (SNMP, SSH, WMI)?
3. **Continuous vs. Scheduled**: flow and log sources benefit from [[ethernet-streamer]] continuous capture; metrics polling uses periodic or cron-based connectors.
4. **Output format**: ensure connector output is parseable — CSV-like for most connectors, binary for [[ethernet-streamer]].

For the Load stage destinations available after extraction and transformation, see [[data-producers]]. For the Transform step between Extract and Load, see [[column-constant-adder]] and the broader [[etl-pipeline]] documentation.
