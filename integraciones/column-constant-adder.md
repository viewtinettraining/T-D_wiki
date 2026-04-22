---
tags: [integraciones, vsdb, transform]
tipo: tecnica
fuentes: ["column-constant-adder"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Column Constant Adder

The Column Constant Adder is a Transform handler in the [[vs-data-broker-overview|VS Data Broker]] [[etl-pipeline]]. It applies a fixed constant value to every record in a specified column, either as a numeric addition or as a string concatenation.

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

In the **Editing Transform Stage** window within the [[plugin-architecture|plugin editor]]:

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

The Column Constant Adder sits in the Transform stage between the Extract and Load phases of the [[etl-pipeline]]. Typical pipeline patterns:

- [[snmp-extractor]] → Column Constant Adder (add site label) → [[data-producers|Producer]]
- [[flow-emitter]] → Column Constant Adder (normalize volume units) → [[data-producers|Producer]]
- [[csv-extractor]] → Column Constant Adder → [[data-producers|Producer]]

For more complex transformations involving conditional logic or field renaming, other Grid Handlers available in the [[customized-plugin]] editor should be used alongside or instead of this handler.
