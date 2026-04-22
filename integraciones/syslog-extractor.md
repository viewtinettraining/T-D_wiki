---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Syslog Extractor'
id: 7QS-BFU-EA1-QA8
slug: syslog-extractor
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Syslog Extractor

The **Syslog Connector** processes syslog messages previously captured by the [Ethernet Streamer](ethernet-streamer.md) connector. It operates as a scheduled pipeline, running periodically to read dumped syslog files, decode the messages, and produce structured fields for further processing in the [ETL pipeline](../conceptos/etl-pipeline.md).

Unlike [NetFlow](netflow-extractor.md), syslog does not require a version selection, which simplifies configuration.

## Key Characteristics

- Depends on a properly configured [Ethernet Streamer](ethernet-streamer.md) pipeline (typically on UDP port 514).
- Supports multi-thread processing for high-volume log environments.
- Parsed syslog records flow into subsequent Transform and Load stages.

## Configuration Parameters

| Parameter | Description |
|---|---|
| **Connector Type** | Syslog Connector |
| **Pipeline Name** | Unique name (e.g., `my_syslog_connector`) |
| **Number of Threads** | Concurrent threads; more threads = faster processing, higher resource usage |
| **Frequency Type** | `Scheduled` (cron) or `Periodic` |
| **Cron Expression** | Execution schedule (e.g., every minute) |
| **Number of Executions** | `-1` for unlimited |
| **Collected Path** | Directory where Ethernet Streamer dumps raw syslog traffic |
| **Processing Path** | Temporary directory for active processing |
| **Processed Path** | Final directory for completed files |
| **Suffix** | File format to process (e.g., `.csv`) |
| **Max Files** | Maximum files per execution cycle |
| **Chunk Size** | Splits large files into smaller segments for efficient processing |

## Example Scenario

If the Ethernet Streamer captures syslog from multiple devices on port 514 and dumps data into `/opt/vn/dhyana/var/data/syslog/collected`, the Syslog Connector will periodically read those files, decode the messages, and output structured records for the [Load stage](data-producers.md).

## Related Pages

- [Ethernet Streamer](ethernet-streamer.md) — Required prerequisite; captures raw syslog traffic
- [Netflow Extractor](netflow-extractor.md) — Similar file-based connector for flow protocols
- [Etl Pipeline](../conceptos/etl-pipeline.md) — Full ETL pipeline context
- [Plugin Categories](../conceptos/plugin-categories.md) — Syslog is a dedicated category in VSDB
- [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) — VSDB product overview
