---
tags: [concepto, plugin, template, vs-data-broker]
tipo: concepto
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Plugin Template

A **plugin template** is a pre-configured [[plugin-architecture|plugin]] distributed by Viewtinet that simplifies the integration of data sources. Templates come with the Extract, Transform, and Load stages — and in many cases dashboards — already configured. They represent the fastest path to integrating a new data source into the [[vs-data-broker-overview|Visual Smart Data Broker]].

## How It Works

Viewtinet maintains a comprehensive library of plugin templates covering different vendors and protocols, including [[snmp-extractor|SNMP]], [[icmp-extractor|ICMP]], [[netflow-extractor|NetFlow]], [[sflow-extractor|sFlow]], and many others. The library is continuously updated as new vendors and protocols become supported.

To use a template:
1. Log into [[viewtimanager-overview|Viewtimanager]].
2. Navigate to the V.S. Data Broker menu.
3. Browse or search the available templates.
4. Select the template and, for most protocol-based templates, simply provide the IP address of the target device.

For SNMP and ICMP-based templates, host provisioning is handled through the [[inventory-management|Inventory]] module rather than by manually entering hosts in the plugin.

## Editing Restrictions

Plugin templates have an important constraint: **it is not recommended to add, change, or delete fields in the Extract, Transform, Load, or Schema stages**. Modifying these stages can cause malfunctions. The only safe extension point is the **decorator feature**, which allows adding new enrichment columns without touching the core pipeline configuration.

## When to Use a Template vs. a Custom Plugin

| Situation | Recommended Approach |
|---|---|
| Vendor or device in the Viewtinet library | Use a [[plugin-template|Plugin Template]] |
| Data source not in the library | Create a [[customized-plugin|Customized Plugin]] |
| Template exists but different fields are needed | Create a [[customized-plugin|Customized Plugin]] |

## Related Concepts

- [[plugin-architecture]] — Full overview of plugin structure
- [[customized-plugin]] — How to build plugins from scratch
- [[plugin-categories]] — Category classification for plugins
- [[etl-pipeline]] — The ETL cycle executed within each plugin
