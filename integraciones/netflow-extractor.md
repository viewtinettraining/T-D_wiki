---
tags: [integracion, netflow, extractor, vs-data-broker]
tipo: tecnica
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# NetFlow Extractor

The **NetFlow Connector** processes flow data (NetFlow, JFlow, NetStream) captured by the [[ethernet-streamer|Ethernet Streamer]] pipeline. Before using this connector, a valid Ethernet Streamer pipeline must be configured with the correct port and host filters (default NetFlow port: UDP/2055). The Ethernet Streamer captures binary traffic and stores it in the Collected Path directory for the NetFlow Connector to decode.

**Note**: Viewtinet provides a [[plugin-template|Plugin Template]] for NetFlow integrations — manual configuration is rarely needed.

## Configuration Parameters

| Parameter | Description |
|---|---|
| **Frequency Type** | `Periodic` (every X seconds) or `Scheduled` (cron expression) |
| **Threads** | Number of concurrent processing threads; more threads increase throughput but use more CPU/memory |
| **Collected Path** | Directory where Ethernet Streamer dumps captured NetFlow files |
| **Processing Path** | Temporary directory for in-progress decoding |
| **Processed Path** | Directory where files are stored after successful processing |
| **Suffix** | File extension of dumped files (typically `.csv`) |
| **Max Files** | Max files per thread execution. Total capacity = `Max Files × Threads` |
| **Number of Executions** | `-1` for continuous; positive integer for limited runs |
| **Version** | NetFlow version for decoding: **5**, **9**, or **IPFIX** |

## Version Selection

The selected NetFlow version determines which fields are decoded and stored. Versions 5, 9, and IPFIX have different field sets. Consistency between the configured version and the actual exporter version is critical.

## Pipeline Flow

```
Ethernet Streamer (listener) → Binary files on disk → NetFlow Connector (decoder) → Transform stage → Load stage
```

## Related Pages

- [[ethernet-streamer]] — Required prerequisite; captures raw NetFlow traffic
- [[sflow-extractor]] — Similar connector for sFlow protocol
- [[etl-pipeline]] — Full ETL pipeline context
- [[plugin-template]] — Pre-built NetFlow plugin template
- [[data-producers]] — Load stage destinations
