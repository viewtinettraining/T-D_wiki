---
tags: [concepto, plugin, schema, vs-data-broker]
tipo: concepto
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Plugin Schema

The **Schema stage** is the fourth stage in a [[etl-pipeline|VSDB pipeline]], following Extract, Transform, and Load. Its purpose is to prepare data structures so they can be used in the [[viewtisight-overview|ViewtiSight]] analytics module.

## Purpose

After data has been extracted and transformed, the Schema stage defines how the data model is exposed for reporting and visualization. It establishes the **metrics** (numerical measures) and **dimensions** (categorical attributes) that describe the collected dataset. Without a schema definition, the pipeline data cannot be consumed by ViewtiSight's Metrics Composer.

## Where It Fits

The schema is defined within each [[plugin-architecture|pipeline]] of a [[plugin-architecture|plugin]]. Both [[plugin-template|plugin templates]] and [[customized-plugin|customized plugins]] include a schema stage:

- In **templates**, the schema is pre-configured and should not be modified.
- In **customized plugins**, the schema must be designed to match the fields produced by the [[etl-pipeline|Transform stage]].

## Relationship to Load

The Schema stage complements the [[data-producers|Load stage]]. While producers route data to storage destinations (e.g., the Viewtinet TSDB via the ViewtinetDB Producer), the schema tells ViewtiSight what that stored data means — which fields are metrics and which are dimensions.

## Key Consideration

The schema definition must align with the field names and types defined in the Extract and Transform stages. Mismatches between the schema and the actual pipeline output will prevent correct metric creation in [[viewtisight-overview|ViewtiSight]].

## Related Pages

- [[etl-pipeline]] — Full pipeline stages overview
- [[plugin-architecture]] — Plugin as container for pipelines and schema
- [[plugin-template]] — Pre-configured schema in templates
- [[customized-plugin]] — Schema definition in custom plugins
- [[viewtisight-overview]] — Analytics module that consumes the schema
- [[data-producers]] — Load stage producers that store data
- [[vs-data-broker-overview]] — VSDB product overview
