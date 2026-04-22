---
tags: [concepto, plugin, categorias, vs-data-broker]
tipo: concepto
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Plugin Categories

Every [[plugin-architecture|plugin]] in the [[vs-data-broker-overview|Visual Smart Data Broker (VSDB)]] belongs to exactly one category. Categories are used to organize and filter plugins in the GUI, enabling administrators to quickly locate the type of integration they need.

## Available Categories

The category panel on the left side of the VSDB interface allows filtering by:

| Category | Typical Use |
|---|---|
| **CDR** | Call Detail Records, VoIP data (pairs with [[csv-extractor|CSV Connector]]) |
| **ICMP** | Reachability monitoring via ping ([[icmp-extractor|ICMP Connector]]) |
| **My Category** | User-defined category for custom grouping |
| **Network** | General network monitoring integrations |
| **Optimization** | QoS and traffic optimization data |
| **SNMP** | Metrics from SNMP-capable devices ([[snmp-extractor|SNMP Connector]]) |
| **SSH** | Server monitoring over SSH ([[ssh-extractor|SSH Query Connector]]) |
| **Sflow** | sFlow traffic data ([[sflow-extractor|sFlow Connector]]) |
| **Syslog** | Log collection ([[syslog-extractor|Syslog Connector]]) |
| **Viewtinet** | Internal Viewtinet integrations (e.g., [[flow-emitter|Flow Emitter]] for [[viewtimon-overview|ViewtiMon]]) |
| **WMI** | Windows management data ([[wmi-extractor|WMI]] or [[windows-remote-management|WinRM]]) |

## How Categories Work

When a user clicks on a category in the left panel, the main workspace filters to show only plugins belonging to that category. This is especially useful in environments with a large number of installed plugins.

## Assigning a Category

When creating a [[customized-plugin|customized plugin]], the category is selected during the initial definition step in the Plugin Creator wizard. It is a required field. [[plugin-template|Plugin templates]] already have their categories pre-assigned by Viewtinet.

## Related Pages

- [[plugin-architecture]] — Plugin structure and lifecycle
- [[plugin-template]] — Pre-built plugins with categories assigned
- [[customized-plugin]] — How to assign a category during creation
- [[etl-pipeline]] — The pipeline inside each plugin
