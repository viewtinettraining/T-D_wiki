---
title: "Data Sources Integration"
description: "Data source integration in Viewtinet is the process of connecting external devices, systems, and services to the platform so their data can be collected, tra..."
keywords: "conceptos, datos, integracion, plugins, etl, protocolos"
---

# Data Sources Integration

Data source integration in Viewtinet is the process of connecting external devices, systems, and services to the platform so their data can be collected, transformed, and analyzed. All integration is handled by the [Visual Smart Data Broker (VSDB)](../productos/vs-data-broker-overview.md) through a [plugin-based ETL architecture](plugin-architecture.md).

## Integration Model

Each integration is defined as a **plugin** — the fundamental unit containing all ETL stages:

- **Extract** — collect raw data from the source using a supported protocol
- **Transform** — normalize, enrich, and reshape the data
- **Load** — deliver processed data to the time-series database or other outputs

Plugins can be created from [Plugin Templates](plugin-architecture.md) (pre-built integrations from the Viewtinet library) or from scratch as [Customized Plugins](customized-plugin.md) using the plugin creator wizard.

## Supported Extraction Protocols

| Protocol | Description |
|----------|-------------|
| SNMP | Polls devices using v1, v2c, or v3; supports OID groups in grid or single-row mode |
| NetFlow / IPFIX | Receives flow data from routers and switches (v5, v9, IPFIX) |
| sFlow | Receives sFlow traffic for sampled packet analysis |
| Syslog | Receives syslog streams from network devices and servers |
| WMI | Windows Management Instrumentation — periodic or scheduled polling |
| SSH Query | Executes commands on remote hosts via SSH |
| ICMP | Ping-based availability and latency monitoring |
| CSV | Reads CSV files from a local or network path |
| Python Task | Executes custom Python scripts for any API or proprietary source |
| Command Executor | Runs arbitrary CLI commands on the Viewtinet host |

For SNMP specifically, hosts are added individually or via CSV bulk import, and OID groups define which OIDs to poll. See [Snmp Extractor](../integraciones/snmp-extractor.md), [Netflow Extractor](../integraciones/netflow-extractor.md), [Sflow Extractor](../integraciones/sflow-extractor.md), and [Syslog Extractor](../integraciones/syslog-extractor.md) for protocol-specific configuration details.

## Transform Stage

After extraction, data passes through configurable transformation handlers:

- Grid Handlers — parse tabular data structures
- Column Constant Adder — inject static metadata columns
- Column Remover — drop unnecessary fields
- Net Decorator — resolve hostnames or enrich with network context
- Date Converter — normalize timestamp formats
- Delta — compute rate-of-change between polling intervals
- Math Operation — apply formulas across columns
- Regex — pattern matching and field extraction
- IP to Country Code — geolocation enrichment

## Load Stage

Processed data can be delivered to multiple destinations simultaneously:

- **Viewtinet Database Producer** — writes to the TimescaleDB time-series database, making data available in [ViewtiSight](../productos/viewtisight-features.md) dashboards
- **CSV Writer / Rotational CSV Writer** — exports to local files
- **Syslog, SCP, Kafka** — forwards to external systems

## Plugin Lifecycle

| Action | Description |
|--------|-------------|
| Install | Activate plugin; data collection begins |
| Uninstall | Deactivate; data erased, config preserved |
| Export | Save plugin definition as JSON for sharing or backup |
| Import | Load a plugin from JSON |
| Clone | Duplicate a plugin as a starting point |
| Erase | Permanently remove plugin and all associated data |

Only installed plugins appear in [ViewtiSight](../productos/viewtisight-features.md) for dashboarding and [alarm configuration](alarms-system.md).

## Plugin Categories

CDR, ICMP, Network, Optimization, SNMP, SSH, Sflow, Syslog, WMI, Viewtinet. Categories are used to organize plugins in the [VSDB](../productos/vs-data-broker-overview.md) interface.

## Related Pages

- [Plugin Architecture](plugin-architecture.md) — internal plugin structure and stages
- [Customized Plugin](customized-plugin.md) — building a plugin from scratch
- [Etl Pipeline](etl-pipeline.md) — full ETL cycle detail
- [Snmp Extractor](../integraciones/snmp-extractor.md), [Netflow Extractor](../integraciones/netflow-extractor.md), [Syslog Extractor](../integraciones/syslog-extractor.md) — protocol extractors
