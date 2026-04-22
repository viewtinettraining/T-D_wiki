---
title: "Python Task Extractor"
description: "The Python Task Connector allows users to integrate custom Python programs into the Visual Smart Data Broker (VSDB). It is the most flexible extraction metho..."
keywords: "integracion, python, extractor, vs-data-broker"
---

# Python Task Extractor

The **Python Task Connector** allows users to integrate custom Python programs into the [Visual Smart Data Broker (VSDB)](../productos/vs-data-broker-overview.md). It is the most flexible extraction method, enabling collection of metrics, logs, or any data accessible via Python code when no standard connector covers the use case.

## Script Requirements

Python scripts must be placed in:
```
/opt/vn/dhyana/bin/
```

Scripts must follow a specific template with two required functions:

```python
import sys
sys.path.append('/app/python-modules/')
from bin.data_wrapper import DataWrapper

_config: dict = None

def init(config: dict):
    global _config
    _config = config  # Receives connector configuration

def read() -> DataWrapper:
    # Implement data collection logic here
    data = DataWrapper.wrap(YOUR_DICT_LIST)
    return data
```

**Critical requirement**: The script must always return data containing a **`timestamp` field in microseconds (16 digits)**. Without it, records cannot be stored in the Viewtinet time-series database.

## Connector Configuration Parameters

| Parameter | Description |
|---|---|
| **Connector Type** | Python Task Connector |
| **Pipeline Name** | Unique name (e.g., `my_python_task`) |
| **Frequency Type** | `Scheduled` (cron) or `Periodic` |
| **Number of Executions** | `-1` for infinite; positive integer limits runs |
| **Program Path** | Directory of the Python script (typically `/opt/vn/dhyana/bin/`) |
| **Module Name** | Script filename without `.py` extension |
| **Main Function** | Entry point function — must be `read` by convention |
| **Arguments** | Optional key-value pairs passed to the script at runtime |
| **Output Fields** | Field definitions matching the dictionary keys returned by the script |

## Output Fields

Output fields must match the keys returned by the `read()` function. The `timestamp` field type must be `ulong`.

Example field configuration:
- `timestamp` → type `ulong` (mandatory)
- `cpu_usage` → type `ulong`

## Related Pages

- [Etl Pipeline](../conceptos/etl-pipeline.md) — Full ETL pipeline context
- [Command Executor](command-executor.md) — Alternative for shell-based custom extraction
- [Csv Extractor](csv-extractor.md) — File-based alternative for structured data
- [Plugin Architecture](../conceptos/plugin-architecture.md) — Plugin container
- [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) — VSDB product overview
