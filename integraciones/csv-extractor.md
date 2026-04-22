---
tags: [integracion, csv, extractor, vs-data-broker]
tipo: tecnica
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# CSV Extractor

The **CSV Connector** ingests records from CSV files stored on the local Viewtilog server. Despite its name, the field separator is configurable, allowing it to handle any delimited file format. It is widely used for integrating VoIP systems — particularly for ingesting CDRs (Call Detail Records) and CMRs (Call Management Records) — as well as any data source that exports logs in CSV format.

## How It Works

An external or scheduled process must deposit CSV files into the configured Collected Path. The connector reads these files, processes them, and moves them to the Processed Path to avoid reprocessing. This file-based approach decouples the data producer from the [[etl-pipeline|ETL pipeline]].

## Configuration Parameters

| Parameter | Description |
|---|---|
| **Frequency Type** | `Periodic` or `Scheduled` (cron expression) |
| **Number of Threads** | Concurrent threads for parallel file processing |
| **Pipeline Name** | Unique pipeline identifier |
| **Refresh Time (secs)** | Interval between runs (Periodic mode) |
| **Number of Executions** | `-1` for continuous; positive integer limits runs |
| **Collected Path** | Directory where new CSV files are placed |
| **Processing Path** | Temporary directory during active processing |
| **Processed Path** | Final directory after processing completes |
| **Separator** | Field delimiter character (`,`, `;`, `|`, etc.) |
| **Suffix** | File extension to process (e.g., `.csv`) |
| **Max Files** | Maximum files processed per cycle |
| **Keep Commas** | Preserves commas inside fields |
| **Has Quotations** | Treats quoted fields as single values even when containing the separator |
| **Chunk Size** | Reads large files in chunks for efficiency |

## Field Definition

Fields must be defined before the connector can parse files. Two methods are available:
1. **Manual entry** — Use the "Add New Field" button; assign name and data type (string, integer, float, etc.)
2. **Import from CSV** — Upload a CSV file containing only the header row; the system auto-creates the field configuration

## Related Pages

- [[etl-pipeline]] — Full ETL pipeline context
- [[plugin-categories]] — CDR is a dedicated category for VoIP CSV data
- [[command-executor]] — Alternative for command-generated CSV-like output
- [[data-producers]] — Load stage destinations after CSV processing
- [[vs-data-broker-overview]] — VSDB product overview
