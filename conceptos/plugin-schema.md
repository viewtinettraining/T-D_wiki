---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Plugin Schema'
id: CPR-B72-Q6X-G5H
slug: plugin-schema
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Plugin Schema

The **Schema stage** is the fourth stage in a [VSDB pipeline](etl-pipeline.md), following Extract, Transform, and Load. Its purpose is to prepare data structures so they can be used in the [ViewtiSight](../productos/viewtisight-overview.md) analytics module.

## Purpose

After data has been extracted and transformed, the Schema stage defines how the data model is exposed for reporting and visualization. It establishes the **metrics** (numerical measures) and **dimensions** (categorical attributes) that describe the collected dataset. Without a schema definition, the pipeline data cannot be consumed by ViewtiSight's Metrics Composer.

## Where It Fits

The schema is defined within each [pipeline](plugin-architecture.md) of a [plugin](plugin-architecture.md). Both [plugin templates](plugin-template.md) and [customized plugins](customized-plugin.md) include a schema stage:

- In **templates**, the schema is pre-configured and should not be modified.
- In **customized plugins**, the schema must be designed to match the fields produced by the [Transform stage](etl-pipeline.md).

## Relationship to Load

The Schema stage complements the [Load stage](../integraciones/data-producers.md). While producers route data to storage destinations (e.g., the Viewtinet TSDB via the ViewtinetDB Producer), the schema tells ViewtiSight what that stored data means — which fields are metrics and which are dimensions.

## Key Consideration

The schema definition must align with the field names and types defined in the Extract and Transform stages. Mismatches between the schema and the actual pipeline output will prevent correct metric creation in [ViewtiSight](../productos/viewtisight-overview.md).

## Related Pages

- [Etl Pipeline](etl-pipeline.md) — Full pipeline stages overview
- [Plugin Architecture](plugin-architecture.md) — Plugin as container for pipelines and schema
- [Plugin Template](plugin-template.md) — Pre-configured schema in templates
- [Customized Plugin](customized-plugin.md) — Schema definition in custom plugins
- [Viewtisight Overview](../productos/viewtisight-overview.md) — Analytics module that consumes the schema
- [Data Producers](../integraciones/data-producers.md) — Load stage producers that store data
- [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) — VSDB product overview
