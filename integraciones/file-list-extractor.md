---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'File List Extractor'
id: XEH-QCA-PD9-XXZ
slug: file-list-extractor
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# File List Extractor

The File List Connector is a scheduled extractor in the [VS Data Broker](../productos/vs-data-broker-overview.md) Extract stage. It reads files from a designated "to-collect" directory on the Viewtilog server and moves them to a "to-send" directory, preparing them for downstream processing or delivery.

This connector is designed for scenarios where external systems drop files — such as CSV logs, call detail records, or reports — into a shared directory for collection. It pairs naturally with the SCP Producer in the Load stage for secure delivery to remote destinations.

## Key Features

- Reads files from a configurable source directory and moves them to an output directory.
- Supports **Periodic** execution (every X seconds) or **Scheduled** execution (cron expression).
- Configurable file suffix filter (e.g., `.csv`) to target specific file types.
- Sets a **maximum file count** per execution to control throughput.
- Works with the SCP Producer to deliver collected files to external systems.

## Difference from Continuous Connectors

Unlike [Ethernet Streamer](ethernet-streamer.md), which runs as a constant listener, the File List Connector operates on a schedule. It activates at defined intervals, processes up to the configured number of files, and then waits until the next execution cycle. This makes it efficient for batch-oriented file ingestion patterns.

## Configuration Steps

1. In the **Editing Extract Stage** window within the [plugin editor](../conceptos/plugin-architecture.md), choose **File List Connector** from the Connector Type dropdown.
2. Enter a unique **Pipeline Name** (e.g., `my_file_list_connector`).
3. Set the **Frequency Type**:
   - **Periodic** — runs every N seconds (set via Refresh Time)
   - **Scheduled** — runs on a cron expression
4. Define the **Paths**:
   - **To-collect path**: directory where files are placed by the external system
   - **To-send path**: directory where files are moved after collection
5. Configure **File Properties**:
   - **Suffix**: file extension to match (e.g., `.csv`)
   - **Max Files**: maximum number of files processed per execution
6. Click **Confirm** to activate the connector.

## Example Configuration

| Parameter | Value |
|---|---|
| Pipeline Name | `my_file_list_connector` |
| Frequency Type | Periodic |
| Refresh Time | 60 seconds |
| Number of Executions | `-1` (indefinite) |
| To-collect Path | `/opt/vn/dhyana/var/data/%%%PLUGIN_NAME%%%/to_collect/` |
| To-send Path | `/opt/vn/dhyana/var/data/%%%PLUGIN_NAME%%%/to_send/` |
| Suffix | `.csv` |
| Max Files | 50 |

## Integration with the ETL Pipeline

After files are moved to the to-send directory, they can be processed through the [Etl Pipeline](../conceptos/etl-pipeline.md) Transform stage for field normalization, then delivered via a [Producer](data-producers.md). The SCP Producer is the most common pairing with this connector, as it securely transfers files to remote destinations.

For context on how this connector fits into a full plugin, see [Customized Plugin](../conceptos/customized-plugin.md) and [Plugin Template](../conceptos/plugin-template.md). For other file-based extraction alternatives, see [Csv Extractor](csv-extractor.md).
