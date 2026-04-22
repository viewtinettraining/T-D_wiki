---
tags: [concepto, etl, pipeline, vs-data-broker]
tipo: concepto
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ETL Pipeline

The **ETL (Extract, Transform, Load) pipeline** is the core processing concept of the [[vs-data-broker-overview|Visual Smart Data Broker (VSDB)]]. Each pipeline defines a sequence of operations that collect raw data from a source, transform it into a structured form, and deliver it to the appropriate destination.

Pipelines are always contained within a [[plugin-architecture|plugin]] — it is not possible to create a pipeline outside of a plugin context.

## Extract Stage

The Extract stage uses **protocol connectors** to acquire data from heterogeneous sources. These sources include:

- Network devices (routers, switches, firewalls) via [[snmp-extractor|SNMP]], [[icmp-extractor|ICMP]], [[netflow-extractor|NetFlow]], [[sflow-extractor|sFlow]]
- Servers via [[ssh-extractor|SSH]], [[wmi-extractor|WMI]], or [[windows-remote-management|WinRM]]
- Log systems via [[syslog-extractor|Syslog]] (captured first by [[ethernet-streamer|Ethernet Streamer]])
- Files via [[csv-extractor|CSV]] or File List Connector
- Databases via [[mongodb-extractor|MongoDB Connector]]
- Custom logic via [[python-task-extractor|Python Task]] or [[command-executor|Command Executor]]
- Internal DPI data via [[flow-emitter|Flow Emitter]] (linked to [[viewtimon-overview|ViewtiMon]])

Connectors support two execution modes: **Periodic** (interval in seconds) or **Scheduled** (cron expression). The Number of Executions parameter controls whether the pipeline runs indefinitely (`-1`) or a fixed number of times.

## Transform Stage

The Transform stage processes ingested data through **Grid Handlers** in sequence. Each handler performs a specific operation:

- **Parsing handler** — Interprets raw messages and extracts fields
- **Normalization handler** — Harmonizes formats into a common schema
- **Math operations handler** — Applies calculations or aggregations
- **Data mapping handler** — Remaps fields into standardized names or structures
- **Enrichment handler** — Adds context such as tags, geolocation, or device metadata
- **[[column-constant-adder|Column Constant Adder]]** — Appends a fixed value to all rows in a column

The goal is to convert heterogeneous raw inputs into coherent, enriched datasets ready for analysis.

## Load Stage

The Load stage routes processed data to its final destination using [[data-producers|Producers]]:

- **ViewtinetDB Producer** — Default; stores data in the Viewtinet Time Series Database (TSDB)
- **CSV Writer / Rotational CSV Writer** — Exports data as CSV files
- **Syslog Producer** — Sends data to a syslog target (SIEM integration)
- **SCP Producer** — Transfers files to a remote server
- **Kafka Producer** — Publishes records to a Kafka topic
- **Aggregator** — Pre-aggregates data before storage

## Schema Stage

The Schema stage is defined within the pipeline to prepare data structures for the [[viewtisight-overview|ViewtiSight]] analytics module. This is where metrics and dimensions are declared, enabling Metrics Composer to build analytical visualizations on top of the loaded data. The [[plugin-schema|plugin schema]] concept covers this in detail.
