---
title: "Plugin Template"
description: "A plugin template is a pre-configured plugin distributed by Viewtinet that simplifies the integration of data sources. Templates come with the Extract, Trans..."
keywords: "concepto, plugin, template, vs-data-broker"
---

# Plugin Template

A **plugin template** is a pre-configured [plugin](plugin-architecture.md) distributed by Viewtinet that simplifies the integration of data sources. Templates come with the Extract, Transform, and Load stages — and in many cases dashboards — already configured. They represent the fastest path to integrating a new data source into the [Visual Smart Data Broker](../productos/vs-data-broker-overview.md).

## How It Works

Viewtinet maintains a comprehensive library of plugin templates covering different vendors and protocols, including [SNMP](../integraciones/snmp-extractor.md), [ICMP](../integraciones/icmp-extractor.md), [NetFlow](../integraciones/netflow-extractor.md), [sFlow](../integraciones/sflow-extractor.md), and many others. The library is continuously updated as new vendors and protocols become supported.

To use a template:
1. Log into [Viewtimanager](../productos/viewtimanager-overview.md).
2. Navigate to the V.S. Data Broker menu.
3. Browse or search the available templates.
4. Select the template and, for most protocol-based templates, simply provide the IP address of the target device.

For SNMP and ICMP-based templates, host provisioning is handled through the [Inventory](../configuracion/inventory-management.md) module rather than by manually entering hosts in the plugin.

## Editing Restrictions

Plugin templates have an important constraint: **it is not recommended to add, change, or delete fields in the Extract, Transform, Load, or Schema stages**. Modifying these stages can cause malfunctions. The only safe extension point is the **decorator feature**, which allows adding new enrichment columns without touching the core pipeline configuration.

## When to Use a Template vs. a Custom Plugin

| Situation | Recommended Approach |
|---|---|
| Vendor or device in the Viewtinet library | Use a [Plugin Template](plugin-template.md) |
| Data source not in the library | Create a [Customized Plugin](customized-plugin.md) |
| Template exists but different fields are needed | Create a [Customized Plugin](customized-plugin.md) |

## Related Concepts

- [Plugin Architecture](plugin-architecture.md) — Full overview of plugin structure
- [Customized Plugin](customized-plugin.md) — How to build plugins from scratch
- [Plugin Categories](plugin-categories.md) — Category classification for plugins
- [Etl Pipeline](etl-pipeline.md) — The ETL cycle executed within each plugin
