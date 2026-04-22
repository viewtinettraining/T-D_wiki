---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Column Constant Adder'
id: 3ST-FFM-GDB-KJN
slug: column-constant-adder
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Column Constant Adder

The Column Constant Adder is a Transform handler in the [VS Data Broker](../productos/vs-data-broker-overview.md) [Etl Pipeline](../conceptos/etl-pipeline.md). It applies a fixed constant value to every record in a specified column, either as a numeric addition or as a string concatenation.

## What It Does

This handler takes two inputs:
1. The **column name** to operate on.
2. The **constant value** to add.

It applies the operation to every row in the dataset and writes the result back into the same column under the same name. No new column is created — the existing column is updated in place.

## Use Cases

**Numeric constant addition**
Add a fixed offset to a numeric column. Useful for unit conversion, bias correction, or normalizing sensor readings across different data sources.

**String concatenation**
Append a constant text string to every value in a string column. Common applications include:
- Adding a suffix to hostnames or device identifiers to indicate source system.
- Prepending a fixed label for routing rules downstream.
- Inserting a constant tenant or site identifier into extracted records.

## How to Configure

In the **Editing Transform Stage** window within the [plugin editor](../conceptos/plugin-architecture.md):

1. Select **Column Constant Adder** from the list of available Grid Handlers.
2. Enter the **column name** to operate on.
3. Enter the **constant** to add (numeric value or text string).
4. Confirm the handler configuration.

The operation is immediately reflected in the transform output preview if a sample dataset is loaded.

## Behavior Notes

- The column name is preserved after the operation — no renaming occurs.
- If the column contains mixed types, results may be unpredictable. Ensure data consistency in the Extract stage before applying this handler.
- Multiple Column Constant Adder handlers can be chained in the same Transform stage to modify several columns independently.

## Context in the ETL Pipeline

The Column Constant Adder sits in the Transform stage between the Extract and Load phases of the [Etl Pipeline](../conceptos/etl-pipeline.md). Typical pipeline patterns:

- [Snmp Extractor](snmp-extractor.md) → Column Constant Adder (add site label) → [Producer](data-producers.md)
- [Flow Emitter](flow-emitter.md) → Column Constant Adder (normalize volume units) → [Producer](data-producers.md)
- [Csv Extractor](csv-extractor.md) → Column Constant Adder → [Producer](data-producers.md)

For more complex transformations involving conditional logic or field renaming, other Grid Handlers available in the [Customized Plugin](../conceptos/customized-plugin.md) editor should be used alongside or instead of this handler.
