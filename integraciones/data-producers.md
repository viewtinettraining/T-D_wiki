---
tags: [integraciones, vsdb, load]
tipo: tecnica
fuentes: ["producers"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Data Producers

Producers are the Load-stage components of the [[vs-data-broker-overview|VS Data Broker]] [[etl-pipeline]]. Once records have been extracted and transformed, a Producer delivers them to their final destination — local storage, a database, a remote file system, a message queue, or an external log receiver.

Configuring a Producer is the final step in building a [[customized-plugin]].

## Available Producer Types

Viewtinet provides seven Producer types, each suited to different output requirements:

### Aggregator
Accumulates records over time before writing them, enabling time-window aggregation. Useful for computing totals, averages, or counts before storing.

### CSV Writer
Writes transformed records to a CSV file on the local Viewtilog server filesystem. Suitable for flat-file exports and local archiving.

### Rotational CSV Writer
Similar to the CSV Writer but automatically rotates the output file at configured intervals (e.g., hourly or daily). Prevents unbounded file growth and facilitates periodic ingestion by external systems.

### Syslog Producer
Sends records as Syslog messages to an external Syslog receiver. Useful for forwarding enriched data to a SIEM, log aggregator, or [[syslog-extractor]]-compatible system.

### SCP Producer
Transfers files securely via SCP (Secure Copy Protocol) to a remote destination. Most commonly paired with the [[file-list-extractor]] connector to move collected files to external systems.

### ViewtinetDB Producer
Writes records directly into the internal Viewtinet database. This is the standard output for data destined for dashboards, [[rest-api]] queries, and reports within the [[viewtimanager-overview]] ecosystem.

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
- [[snmp-extractor]] → [[column-constant-adder]] → ViewtinetDB Producer
- [[ethernet-streamer]] → [[netflow-extractor]] → Kafka Producer
- [[file-list-extractor]] → CSV Writer → SCP Producer

For full plugin construction details, see [[customized-plugin]] and [[plugin-template]]. For an overview of all Extract-stage options, see [[data-sources-overview]].
