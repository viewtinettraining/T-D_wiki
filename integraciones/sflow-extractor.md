---
tags: [integracion, sflow, extractor, vs-data-broker]
tipo: tecnica
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# sFlow Extractor

The **sFlow Connector** processes flow data exported in the **sFlow protocol** from network switches and routers. Like the [[netflow-extractor|NetFlow Connector]], it requires a prerequisite [[ethernet-streamer|Ethernet Streamer]] pipeline to be configured first — the Ethernet Streamer listens on the sFlow port (commonly UDP/6343), captures binary traffic, and deposits it in the Collected Path for the sFlow Connector to decode.

**Note**: Viewtinet provides a [[plugin-template|Plugin Template]] for sFlow integrations. In most cases the template already includes a functional setup.

## Configuration Parameters

| Parameter | Description |
|---|---|
| **Frequency Type** | `Periodic` (every X seconds) or `Scheduled` (cron expression) |
| **Threads** | Concurrent processing threads; increases throughput at the cost of CPU/memory |
| **Collected Path** | Directory where Ethernet Streamer dumps captured sFlow files |
| **Processing Path** | Temporary directory for in-progress decoding |
| **Processed Path** | Directory where successfully processed files are stored |
| **Suffix** | File extension of dumped files (`.csv` or binary format) |
| **Max Files** | Maximum files processed per thread per execution cycle |
| **Number of Executions** | `-1` for indefinite; positive integer limits runs |
| **Version** | sFlow standard version for field decoding; typically **sFlow v5** |

## Relationship to Ethernet Streamer

The Ethernet Streamer and sFlow Connector work as a two-stage pair within the [[etl-pipeline|ETL pipeline]]:
1. **Ethernet Streamer** — Passive listener; captures raw sFlow UDP traffic continuously.
2. **sFlow Connector** — Scheduled decoder; reads binary dumps and extracts structured fields.

## Related Pages

- [[ethernet-streamer]] — Required prerequisite for traffic capture
- [[netflow-extractor]] — Similar connector for NetFlow/JFlow/NetStream
- [[etl-pipeline]] — Full ETL pipeline context
- [[plugin-template]] — Pre-built sFlow plugin template
- [[plugin-categories]] — Sflow is a dedicated category in VSDB
