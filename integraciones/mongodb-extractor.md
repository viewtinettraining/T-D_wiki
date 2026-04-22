---
title: "MongoDB Extractor"
description: "The MongoDB Connector extracts data directly from a MongoDB collection into the Visual Smart Data Broker ETL pipeline. It is useful for integrating structure..."
keywords: "integracion, mongodb, extractor, vs-data-broker"
---

# MongoDB Extractor

The **MongoDB Connector** extracts data directly from a MongoDB collection into the [Visual Smart Data Broker](../productos/vs-data-broker-overview.md) [ETL pipeline](../conceptos/etl-pipeline.md). It is useful for integrating structured JSON documents from external applications such as alarms, logs, or metadata. Unlike passive listeners such as the [Ethernet Streamer](ethernet-streamer.md), the MongoDB Connector is a **scheduled connector** that runs periodically.

## Key Features

- Connects to MongoDB using a standard URI
- Supports `Periodic` or `Scheduled` (cron) execution
- Uses a **time filter column** to read only new documents since the last run
- Tracks the last read position via a `.tf` tracking file to prevent duplicate copies
- Supports selective field extraction from MongoDB documents

## Configuration Parameters

| Parameter | Description |
|---|---|
| **Connection URI** | MongoDB connection string (e.g., `mongodb://username:password@127.0.0.1:27017`) |
| **Database** | Database name (e.g., `viewtinet`) |
| **Collection** | Collection to extract from (e.g., `alarms`) |
| **Batch Size** | Max documents per run (default: 1,000,000). Low values risk falling behind rapid data ingestion |
| **Time Filter Column** | Field used to sort and filter; typically a timestamp field like `__ttl_created_at` |
| **Time Filter Starting Value** | Initial value in ms/ns; `0` or empty copies all documents |
| **Time Filter File Path** | Location of the `.tf` tracking file — deleting this restarts from scratch |
| **Fields** | List of document keys to extract as columns |

## Field Extraction Notes

MongoDB documents are stored as JSON. Top-level keys are extracted as string columns. For **nested JSON** (e.g., `owner.name`), use the **JsonParser Grid Handler** in the Transform stage to extract sub-fields.

Example document:
```json
{"uuid": "e4c2ebe9...", "created_at": "2022-10-18T14:37:03Z", "owner": {"name": "admin", "tenant": "Viewtinet"}}
```

The `owner` field is extracted as a JSON string; parsing `owner.name` requires a Transform-stage handler.

## Related Pages

- [Etl Pipeline](../conceptos/etl-pipeline.md) — Full ETL pipeline context
- [Ethernet Streamer](ethernet-streamer.md) — Passive listener alternative for network traffic
- [Python Task Extractor](python-task-extractor.md) — Custom extraction for complex data sources
- [Data Producers](data-producers.md) — Load stage destinations
- [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) — VSDB product overview
