---
tags: [fuentes, datos, integracion, plugins]
tipo: fuente
fuentes: ["data-sources-integration-guide_en_v6.3"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Data Sources Integration Guide PDF — Source Summary

This page summarizes the Data Sources Integration Guide (v6.3), covering the Visual Smart Data Broker (VSDB) and the full [[data-sources-integration|ETL pipeline]] for integrating any data source into the Viewtinet platform.

## Core Concepts

- **Smart Data Broker (SDB)** — Viewtinet's engine for integrating data sources in any format from any vendor via multiple protocols
- **Plugin** — the fundamental unit containing ETL stages (Extract, Transform, Load, Schema, Dashboards)
- **Plugin Template** — pre-configured plugins from the Viewtinet library; not to be structurally edited
- **Customized Plugin** — user-created via Plugin Creator for custom data sources

Data loaded by plugins is stored in a time-series database (TimescaleDB via [[vs-data-broker-overview|Viewticore]]) and becomes accessible in [[viewtisight-features|ViewtiSight]] for dashboarding.

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

For SNMP, hosts are added individually or via CSV import. OID groups define which OIDs to poll per host. See [[snmp-extractor]] and [[netflow-extractor]] for protocol-specific details.

## Transform Stage

Transformations include: Grid Handlers, Column Constant Adder, Column Remover, [[data-sources-integration|CSV Decorator]], Net Decorator, Date Converter, Delta, Key Value, Math Operation, Regex, Split, IP to Country Code.

## Load Stage

Supports output to: CSV Writer, [[vs-data-broker-overview|Viewtinet Database Producer]] (TimescaleDB), Rotational CSV Writer. Multiple outputs can run simultaneously.

## Plugin Lifecycle

Plugins can be installed, uninstalled (data erased, config kept), exported (JSON), imported, cloned, or erased. Only installed plugins appear in [[viewtisight-features|ViewtiSight]].

## Plugin Categories

CDR, ICMP, My Category, Network, Optimization, SNMP, SSH, Sflow, Syslog, Viewtinet, WMI.

## Related Pages

- [[data-sources-integration]] — conceptual overview
- [[data-sources-overview]] — supported data source types
- [[plugin-architecture]] — plugin system internals
- [[snmp-extractor]], [[netflow-extractor]], [[syslog-extractor]] — protocol extractors
