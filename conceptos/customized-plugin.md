---
title: "Customized Plugin"
description: "A customized plugin is a plugin created from scratch using the Plugin Creator wizard in the Visual Smart Data Broker (VSDB). Unlike plugin templates, which a..."
keywords: "concepto, plugin, customizado, vs-data-broker"
---

# Customized Plugin

A **customized plugin** is a [plugin](plugin-architecture.md) created from scratch using the Plugin Creator wizard in the [Visual Smart Data Broker (VSDB)](../productos/vs-data-broker-overview.md). Unlike [plugin templates](plugin-template.md), which are pre-built by Viewtinet, customized plugins are fully defined by the administrator.

## When to Create a Customized Plugin

There are two primary reasons to create a customized plugin:

1. **The data source is not available in the template library** — When a vendor, device, or protocol is not covered by any existing [template](plugin-template.md), a new plugin must be built from scratch.
2. **Custom field selection** — Even when a vendor appears in the library, you may need to collect different OIDs, log fields, or metrics than what the template provides.

## Creation Process

The Plugin Creator wizard guides the administrator through six steps:

1. **Define the Plugin Container** — Assign a name, description, [category](plugin-categories.md), and module dependencies. Optionally, add an identifying image.
2. **Configure the Extract Stage** — Select and configure protocol connectors such as [SNMP](../integraciones/snmp-extractor.md), [ICMP](../integraciones/icmp-extractor.md), [Syslog](../integraciones/syslog-extractor.md), [CSV](../integraciones/csv-extractor.md), [SSH](../integraciones/ssh-extractor.md), [Python Task](../integraciones/python-task-extractor.md), or others.
3. **Design the Transform Stage** — Add Grid Handlers to parse, normalize, enrich, and calculate fields. The [Column Constant Adder](../integraciones/column-constant-adder.md) is one example.
4. **Configure the Load Stage** — Choose [producers](../integraciones/data-producers.md) to determine where the data is stored (Viewtinet TSDB, Syslog export, SCP, CSV, Kafka).
5. **Integrate Dashboards and Reports** — Link the plugin to existing dashboards or create new visualizations.
6. **Save and Validate** — Deploy the plugin and verify that data sources are processed correctly.

## Plugin Metadata

Each customized plugin requires:
- **Name**: Descriptive identifier
- **Category**: Selected from the [available categories](plugin-categories.md)
- **Description**: Purpose and coverage of the plugin
- **Dependencies**: Viewtinet modules required to run the plugin

## Post-Creation Operations

After creation, customized plugins support the same lifecycle operations as templates: editing, cloning, exporting as JSON, and importing. The [schema stage](plugin-schema.md) within the pipeline must be defined to make data available for [ViewtiSight](../productos/viewtisight-overview.md) analytics.
