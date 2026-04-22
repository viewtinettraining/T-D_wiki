---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Plugin Categories'
id: LJ2-J5Q-INA-JKS
slug: plugin-categories
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Plugin Categories

Every [plugin](plugin-architecture.md) in the [Visual Smart Data Broker (VSDB)](../productos/vs-data-broker-overview.md) belongs to exactly one category. Categories are used to organize and filter plugins in the GUI, enabling administrators to quickly locate the type of integration they need.

## Available Categories

The category panel on the left side of the VSDB interface allows filtering by:

| Category | Typical Use |
|---|---|
| **CDR** | Call Detail Records, VoIP data (pairs with [CSV Connector](../integraciones/csv-extractor.md)) |
| **ICMP** | Reachability monitoring via ping ([ICMP Connector](../integraciones/icmp-extractor.md)) |
| **My Category** | User-defined category for custom grouping |
| **Network** | General network monitoring integrations |
| **Optimization** | QoS and traffic optimization data |
| **SNMP** | Metrics from SNMP-capable devices ([SNMP Connector](../integraciones/snmp-extractor.md)) |
| **SSH** | Server monitoring over SSH ([SSH Query Connector](../integraciones/ssh-extractor.md)) |
| **Sflow** | sFlow traffic data ([sFlow Connector](../integraciones/sflow-extractor.md)) |
| **Syslog** | Log collection ([Syslog Connector](../integraciones/syslog-extractor.md)) |
| **Viewtinet** | Internal Viewtinet integrations (e.g., [Flow Emitter](../integraciones/flow-emitter.md) for [ViewtiMon](../productos/viewtimon-overview.md)) |
| **WMI** | Windows management data ([WMI](../integraciones/wmi-extractor.md) or [WinRM](../integraciones/windows-remote-management.md)) |

## How Categories Work

When a user clicks on a category in the left panel, the main workspace filters to show only plugins belonging to that category. This is especially useful in environments with a large number of installed plugins.

## Assigning a Category

When creating a [customized plugin](customized-plugin.md), the category is selected during the initial definition step in the Plugin Creator wizard. It is a required field. [Plugin templates](plugin-template.md) already have their categories pre-assigned by Viewtinet.

## Related Pages

- [Plugin Architecture](plugin-architecture.md) — Plugin structure and lifecycle
- [Plugin Template](plugin-template.md) — Pre-built plugins with categories assigned
- [Customized Plugin](customized-plugin.md) — How to assign a category during creation
- [Etl Pipeline](etl-pipeline.md) — The pipeline inside each plugin
