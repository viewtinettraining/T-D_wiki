---
tags: [integraciones, vsdb, extractor]
tipo: tecnica
fuentes: ["command-executor"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Command Executor

The Command Executor Connector allows the [[vs-data-broker-overview|VS Data Broker]] to run arbitrary shell commands or scripts as an Extract stage source. Any command-line tool or script accessible on the host system can be used, making this the most flexible extractor in the [[plugin-architecture]].

The output of the executed command is parsed the same way as [[csv-extractor]] data: fields must be defined manually or imported using header-based sample files.

## Configuration Parameters

**Frequency Type**
- **Periodic**: executes the pipeline at fixed intervals defined by Refresh Time (seconds).
- **Scheduled**: uses a cron expression to define exact execution times.

**Number of Executions**
- `-1`: runs indefinitely.
- Positive integer: stops after the specified number of runs.

**Command**
The command or bash script to execute. Clicking the pencil icon opens an inline editor where multi-line scripts can be written. The script must produce structured output (CSV-like format) that the connector can parse.

## How It Works

1. At each execution interval, the configured command or script is run on the host system.
2. The command's standard output is captured by the connector.
3. The output is parsed identically to [[csv-extractor]] data:
   - Fields can be defined manually in the schema editor, or
   - Imported from a sample output file using the header row.
4. The parsed records flow into the Transform stage of the [[etl-pipeline]].

## Typical Use Cases

- **OS metrics not available via SNMP**: bash scripts querying `/proc` or system counters.
- **Database queries**: scripts running SQL queries that return CSV-formatted results.
- **API calls**: using `curl` or similar CLI tools to call REST APIs and capture the response.
- **Custom application logs**: scripts that tail or parse application-specific log formats.
- **Python scripts**: equivalent to [[python-task-extractor]] for script-based collection.

## Field Definition

Because the Command Executor uses the same parsing model as [[csv-extractor]], the output structure must be consistent across executions. Variable-schema outputs will cause parsing errors. Define all expected fields in the connector's schema configuration before activating the pipeline.

## Integration with the ETL Pipeline

After extraction, records pass through the Transform stage (e.g., [[column-constant-adder]] for enrichment) and then to a [[data-producers|Producer]] for storage or export.

For a complete walkthrough of building a plugin using this connector, see [[customized-plugin]] and [[plugin-template]]. For simpler structured extraction with no scripting, consider [[csv-extractor]], [[snmp-extractor]], or [[wmi-extractor]] depending on the data source.
