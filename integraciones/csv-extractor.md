---
title: "CSV Extractor"
description: "The CSV Connector ingests records from CSV files stored on the local Viewtilog server. Despite its name, the field separator is configurable, allowing it to ..."
keywords: "integracion, csv, extractor, vs-data-broker"
---

# CSV Extractor

The **CSV Connector** ingests records from CSV files stored on the local Viewtilog server. Despite its name, the field separator is configurable, allowing it to handle any delimited file format. It is widely used for integrating VoIP systems — particularly for ingesting CDRs (Call Detail Records) and CMRs (Call Management Records) — as well as any data source that exports logs in CSV format.

## How It Works

An external or scheduled process must deposit CSV files into the configured Collected Path. The connector reads these files, processes them, and moves them to the Processed Path to avoid reprocessing. This file-based approach decouples the data producer from the [ETL pipeline](../conceptos/etl-pipeline.md).

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

- [Etl Pipeline](../conceptos/etl-pipeline.md) — Full ETL pipeline context
- [Plugin Categories](../conceptos/plugin-categories.md) — CDR is a dedicated category for VoIP CSV data
- [Command Executor](command-executor.md) — Alternative for command-generated CSV-like output
- [Data Producers](data-producers.md) — Load stage destinations after CSV processing
- [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) — VSDB product overview
