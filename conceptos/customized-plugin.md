---
tags: [concepto, plugin, customizado, vs-data-broker]
tipo: concepto
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Customized Plugin

A **customized plugin** is a [[plugin-architecture|plugin]] created from scratch using the Plugin Creator wizard in the [[vs-data-broker-overview|Visual Smart Data Broker (VSDB)]]. Unlike [[plugin-template|plugin templates]], which are pre-built by Viewtinet, customized plugins are fully defined by the administrator.

## When to Create a Customized Plugin

There are two primary reasons to create a customized plugin:

1. **The data source is not available in the template library** — When a vendor, device, or protocol is not covered by any existing [[plugin-template|template]], a new plugin must be built from scratch.
2. **Custom field selection** — Even when a vendor appears in the library, you may need to collect different OIDs, log fields, or metrics than what the template provides.

## Creation Process

The Plugin Creator wizard guides the administrator through six steps:

1. **Define the Plugin Container** — Assign a name, description, [[plugin-categories|category]], and module dependencies. Optionally, add an identifying image.
2. **Configure the Extract Stage** — Select and configure protocol connectors such as [[snmp-extractor|SNMP]], [[icmp-extractor|ICMP]], [[syslog-extractor|Syslog]], [[csv-extractor|CSV]], [[ssh-extractor|SSH]], [[python-task-extractor|Python Task]], or others.
3. **Design the Transform Stage** — Add Grid Handlers to parse, normalize, enrich, and calculate fields. The [[column-constant-adder|Column Constant Adder]] is one example.
4. **Configure the Load Stage** — Choose [[data-producers|producers]] to determine where the data is stored (Viewtinet TSDB, Syslog export, SCP, CSV, Kafka).
5. **Integrate Dashboards and Reports** — Link the plugin to existing dashboards or create new visualizations.
6. **Save and Validate** — Deploy the plugin and verify that data sources are processed correctly.

## Plugin Metadata

Each customized plugin requires:
- **Name**: Descriptive identifier
- **Category**: Selected from the [[plugin-categories|available categories]]
- **Description**: Purpose and coverage of the plugin
- **Dependencies**: Viewtinet modules required to run the plugin

## Post-Creation Operations

After creation, customized plugins support the same lifecycle operations as templates: editing, cloning, exporting as JSON, and importing. The [[plugin-schema|schema stage]] within the pipeline must be defined to make data available for [[viewtisight-overview|ViewtiSight]] analytics.
