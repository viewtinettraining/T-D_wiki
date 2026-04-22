---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'sFlow Extractor'
id: 4J5-RW8-EPY-POU
slug: sflow-extractor
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# sFlow Extractor

The **sFlow Connector** processes flow data exported in the **sFlow protocol** from network switches and routers. Like the [NetFlow Connector](netflow-extractor.md), it requires a prerequisite [Ethernet Streamer](ethernet-streamer.md) pipeline to be configured first — the Ethernet Streamer listens on the sFlow port (commonly UDP/6343), captures binary traffic, and deposits it in the Collected Path for the sFlow Connector to decode.

**Note**: Viewtinet provides a [Plugin Template](../conceptos/plugin-template.md) for sFlow integrations. In most cases the template already includes a functional setup.

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

The Ethernet Streamer and sFlow Connector work as a two-stage pair within the [ETL pipeline](../conceptos/etl-pipeline.md):
1. **Ethernet Streamer** — Passive listener; captures raw sFlow UDP traffic continuously.
2. **sFlow Connector** — Scheduled decoder; reads binary dumps and extracts structured fields.

## Related Pages

- [Ethernet Streamer](ethernet-streamer.md) — Required prerequisite for traffic capture
- [Netflow Extractor](netflow-extractor.md) — Similar connector for NetFlow/JFlow/NetStream
- [Etl Pipeline](../conceptos/etl-pipeline.md) — Full ETL pipeline context
- [Plugin Template](../conceptos/plugin-template.md) — Pre-built sFlow plugin template
- [Plugin Categories](../conceptos/plugin-categories.md) — Sflow is a dedicated category in VSDB
