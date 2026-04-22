---
title: "Data Sources Integration Guide PDF — Source Summary"
description: "This page summarizes the Data Sources Integration Guide (v6.3), covering the Visual Smart Data Broker (VSDB) and the full ETL pipeline for integrating any da..."
keywords: "fuentes, datos, integracion, plugins"
---

# Data Sources Integration Guide PDF — Source Summary

This page summarizes the Data Sources Integration Guide (v6.3), covering the Visual Smart Data Broker (VSDB) and the full [ETL pipeline](../conceptos/data-sources-integration.md) for integrating any data source into the Viewtinet platform.

## Core Concepts

- **Smart Data Broker (SDB)** — Viewtinet's engine for integrating data sources in any format from any vendor via multiple protocols
- **Plugin** — the fundamental unit containing ETL stages (Extract, Transform, Load, Schema, Dashboards)
- **Plugin Template** — pre-configured plugins from the Viewtinet library; not to be structurally edited
- **Customized Plugin** — user-created via Plugin Creator for custom data sources

Data loaded by plugins is stored in a time-series database (TimescaleDB via [Viewticore](../productos/vs-data-broker-overview.md)) and becomes accessible in [ViewtiSight](../productos/viewtisight-features.md) for dashboarding.

## Extract Stage — Supported Protocols

| Protocol | Description |
|----------|-------------|
| SNMP | Polls devices using v1, v2c, or v3; supports OID groups in grid or single-row mode |
| NetFlow | Listens on an interface for v5, v9, or IPFIX traffic |
| WMI | Windows Management Instrumentation periodic or scheduled polling |
| Syslog | Receives syslog streams |
| CSV | Reads CSV files from a path using periodic or cron schedule |
| Python Task | Executes custom Python scripts |
| SSH Query | Executes commands via SSH |
| ICMP | Ping-based monitoring |
| SFlow | Receives SFlow traffic |
| Command Executor | Runs arbitrary CLI commands |

For SNMP, hosts are added individually or via CSV import. OID groups define which OIDs to poll per host. See [Snmp Extractor](../integraciones/snmp-extractor.md) and [Netflow Extractor](../integraciones/netflow-extractor.md) for protocol-specific details.

## Transform Stage

Transformations include: Grid Handlers, Column Constant Adder, Column Remover, [CSV Decorator](../conceptos/data-sources-integration.md), Net Decorator, Date Converter, Delta, Key Value, Math Operation, Regex, Split, IP to Country Code.

## Load Stage

Supports output to: CSV Writer, [Viewtinet Database Producer](../productos/vs-data-broker-overview.md) (TimescaleDB), Rotational CSV Writer. Multiple outputs can run simultaneously.

## Plugin Lifecycle

Plugins can be installed, uninstalled (data erased, config kept), exported (JSON), imported, cloned, or erased. Only installed plugins appear in [ViewtiSight](../productos/viewtisight-features.md).

## Plugin Categories

CDR, ICMP, My Category, Network, Optimization, SNMP, SSH, Sflow, Syslog, Viewtinet, WMI.

## Related Pages

- [Data Sources Integration](../conceptos/data-sources-integration.md) — conceptual overview
- [Data Sources Overview](../integraciones/data-sources-overview.md) — supported data source types
- [Plugin Architecture](../conceptos/plugin-architecture.md) — plugin system internals
- [Snmp Extractor](../integraciones/snmp-extractor.md), [Netflow Extractor](../integraciones/netflow-extractor.md), [Syslog Extractor](../integraciones/syslog-extractor.md) — protocol extractors
