---
title: "ETL Pipeline"
description: "The ETL (Extract, Transform, Load) pipeline is the core processing concept of the Visual Smart Data Broker (VSDB). Each pipeline defines a sequence of operat..."
keywords: "concepto, etl, pipeline, vs-data-broker"
---

# ETL Pipeline

The **ETL (Extract, Transform, Load) pipeline** is the core processing concept of the [Visual Smart Data Broker (VSDB)](../productos/vs-data-broker-overview.md). Each pipeline defines a sequence of operations that collect raw data from a source, transform it into a structured form, and deliver it to the appropriate destination.

Pipelines are always contained within a [plugin](plugin-architecture.md) — it is not possible to create a pipeline outside of a plugin context.

## Extract Stage

The Extract stage uses **protocol connectors** to acquire data from heterogeneous sources. These sources include:

- Network devices (routers, switches, firewalls) via [SNMP](../integraciones/snmp-extractor.md), [ICMP](../integraciones/icmp-extractor.md), [NetFlow](../integraciones/netflow-extractor.md), [sFlow](../integraciones/sflow-extractor.md)
- Servers via [SSH](../integraciones/ssh-extractor.md), [WMI](../integraciones/wmi-extractor.md), or [WinRM](../integraciones/windows-remote-management.md)
- Log systems via [Syslog](../integraciones/syslog-extractor.md) (captured first by [Ethernet Streamer](../integraciones/ethernet-streamer.md))
- Files via [CSV](../integraciones/csv-extractor.md) or File List Connector
- Databases via [MongoDB Connector](../integraciones/mongodb-extractor.md)
- Custom logic via [Python Task](../integraciones/python-task-extractor.md) or [Command Executor](../integraciones/command-executor.md)
- Internal DPI data via [Flow Emitter](../integraciones/flow-emitter.md) (linked to [ViewtiMon](../productos/viewtimon-overview.md))

Connectors support two execution modes: **Periodic** (interval in seconds) or **Scheduled** (cron expression). The Number of Executions parameter controls whether the pipeline runs indefinitely (`-1`) or a fixed number of times.

## Transform Stage

The Transform stage processes ingested data through **Grid Handlers** in sequence. Each handler performs a specific operation:

- **Parsing handler** — Interprets raw messages and extracts fields
- **Normalization handler** — Harmonizes formats into a common schema
- **Math operations handler** — Applies calculations or aggregations
- **Data mapping handler** — Remaps fields into standardized names or structures
- **Enrichment handler** — Adds context such as tags, geolocation, or device metadata
- **[Column Constant Adder](../integraciones/column-constant-adder.md)** — Appends a fixed value to all rows in a column

The goal is to convert heterogeneous raw inputs into coherent, enriched datasets ready for analysis.

## Load Stage

The Load stage routes processed data to its final destination using [Producers](../integraciones/data-producers.md):

- **ViewtinetDB Producer** — Default; stores data in the Viewtinet Time Series Database (TSDB)
- **CSV Writer / Rotational CSV Writer** — Exports data as CSV files
- **Syslog Producer** — Sends data to a syslog target (SIEM integration)
- **SCP Producer** — Transfers files to a remote server
- **Kafka Producer** — Publishes records to a Kafka topic
- **Aggregator** — Pre-aggregates data before storage

## Schema Stage

The Schema stage is defined within the pipeline to prepare data structures for the [ViewtiSight](../productos/viewtisight-overview.md) analytics module. This is where metrics and dimensions are declared, enabling Metrics Composer to build analytical visualizations on top of the loaded data. The [plugin schema](plugin-schema.md) concept covers this in detail.
