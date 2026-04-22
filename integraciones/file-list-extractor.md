---
tags: [integraciones, vsdb, extractor]
tipo: tecnica
fuentes: ["file-list"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# File List Extractor

The File List Connector is a scheduled extractor in the [[vs-data-broker-overview|VS Data Broker]] Extract stage. It reads files from a designated "to-collect" directory on the Viewtilog server and moves them to a "to-send" directory, preparing them for downstream processing or delivery.

This connector is designed for scenarios where external systems drop files — such as CSV logs, call detail records, or reports — into a shared directory for collection. It pairs naturally with the SCP Producer in the Load stage for secure delivery to remote destinations.

## Key Features

- Reads files from a configurable source directory and moves them to an output directory.
- Supports **Periodic** execution (every X seconds) or **Scheduled** execution (cron expression).
- Configurable file suffix filter (e.g., `.csv`) to target specific file types.
- Sets a **maximum file count** per execution to control throughput.
- Works with the SCP Producer to deliver collected files to external systems.

## Difference from Continuous Connectors

Unlike [[ethernet-streamer]], which runs as a constant listener, the File List Connector operates on a schedule. It activates at defined intervals, processes up to the configured number of files, and then waits until the next execution cycle. This makes it efficient for batch-oriented file ingestion patterns.

## Configuration Steps

1. In the **Editing Extract Stage** window within the [[plugin-architecture|plugin editor]], choose **File List Connector** from the Connector Type dropdown.
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

After files are moved to the to-send directory, they can be processed through the [[etl-pipeline]] Transform stage for field normalization, then delivered via a [[data-producers|Producer]]. The SCP Producer is the most common pairing with this connector, as it securely transfers files to remote destinations.

For context on how this connector fits into a full plugin, see [[customized-plugin]] and [[plugin-template]]. For other file-based extraction alternatives, see [[csv-extractor]].
