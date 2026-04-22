---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Data Producers'
id: SY1-U0M-E7H-KBG
slug: data-producers
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Data Producers

Producers are the Load-stage components of the [VS Data Broker](../productos/vs-data-broker-overview.md) [Etl Pipeline](../conceptos/etl-pipeline.md). Once records have been extracted and transformed, a Producer delivers them to their final destination — local storage, a database, a remote file system, a message queue, or an external log receiver.

Configuring a Producer is the final step in building a [Customized Plugin](../conceptos/customized-plugin.md).

## Available Producer Types

Viewtinet provides seven Producer types, each suited to different output requirements:

### Aggregator
Accumulates records over time before writing them, enabling time-window aggregation. Useful for computing totals, averages, or counts before storing.

### CSV Writer
Writes transformed records to a CSV file on the local Viewtilog server filesystem. Suitable for flat-file exports and local archiving.

### Rotational CSV Writer
Similar to the CSV Writer but automatically rotates the output file at configured intervals (e.g., hourly or daily). Prevents unbounded file growth and facilitates periodic ingestion by external systems.

### Syslog Producer
Sends records as Syslog messages to an external Syslog receiver. Useful for forwarding enriched data to a SIEM, log aggregator, or [Syslog Extractor](syslog-extractor.md)-compatible system.

### SCP Producer
Transfers files securely via SCP (Secure Copy Protocol) to a remote destination. Most commonly paired with the [File List Extractor](file-list-extractor.md) connector to move collected files to external systems.

### ViewtinetDB Producer
Writes records directly into the internal Viewtinet database. This is the standard output for data destined for dashboards, [Rest Api](../productos/rest-api.md) queries, and reports within the [Viewtimanager Overview](../productos/viewtimanager-overview.md) ecosystem.

### Kafka Producer
Publishes records to an Apache Kafka topic. Enables integration with streaming analytics platforms and external data pipelines that consume from Kafka.

## Choosing a Producer

| Scenario | Recommended Producer |
|---|---|
| Internal dashboards and reports | ViewtinetDB Producer |
| Forwarding to a SIEM | Syslog Producer |
| Delivering files to external systems | SCP Producer |
| Streaming to Kafka consumers | Kafka Producer |
| Local flat-file archiving | CSV Writer / Rotational CSV Writer |
| Time-window aggregation before storing | Aggregator |

## Integration with the ETL Pipeline

Producers consume the output of the Transform stage. A minimal pipeline looks like:

```
Extract (Connector) → Transform (Grid Handlers) → Load (Producer)
```

Examples:
- [Snmp Extractor](snmp-extractor.md) → [Column Constant Adder](column-constant-adder.md) → ViewtinetDB Producer
- [Ethernet Streamer](ethernet-streamer.md) → [Netflow Extractor](netflow-extractor.md) → Kafka Producer
- [File List Extractor](file-list-extractor.md) → CSV Writer → SCP Producer

For full plugin construction details, see [Customized Plugin](../conceptos/customized-plugin.md) and [Plugin Template](../conceptos/plugin-template.md). For an overview of all Extract-stage options, see [Data Sources Overview](data-sources-overview.md).
