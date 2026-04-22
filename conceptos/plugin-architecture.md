---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Plugin Architecture'
id: WKK-0CR-UPY-P34
slug: plugin-architecture
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Plugin Architecture

In the [Visual Smart Data Broker (VSDB)](../productos/vs-data-broker-overview.md), a **plugin** is the fundamental organizational unit. It acts as a mandatory container for one or more [ETL pipelines](etl-pipeline.md). No pipeline can exist outside of a plugin — the plugin provides the framework where pipelines are defined, documented, and linked to dashboards, alarms, and reports.

## What a Plugin Contains

A plugin is composed of:

- **One or more Pipelines** — Each pipeline executes the full ETL cycle: Extract, Transform, Load, and Schema stages.
- **Name** — A descriptive label (e.g., "Fortinet Network Monitoring Template").
- **Category** — Classification into [a named category](plugin-categories.md) such as SNMP, Syslog, SSH, Network, WMI, etc.
- **Description** — A human-readable summary of what the plugin collects.
- **Dependencies** — Modules required for the plugin to function.
- **Image** — An optional JPG/PNG image to visually identify the plugin.

## Two Plugin Types

There are two types of plugins in VSDB:

1. **[Plugin Templates](plugin-template.md)** — Pre-built integrations distributed by Viewtinet. These come with Extract, Transform, Load stages and dashboards already configured. In most cases, only the target IP address is needed to deploy them.

2. **[Customized Plugins](customized-plugin.md)** — Created from scratch using the Plugin Creator wizard when a data source is not available in the template library, or when custom fields are required beyond what a template provides.

## Plugin Lifecycle

- **Create**: Use the "Create New Plugin" button in the [VSDB](../productos/vs-data-broker-overview.md) GUI.
- **Edit**: Each pipeline stage can be modified individually via the Edit button.
- **Clone**: An exact copy can be created without affecting existing installations.
- **Export/Import**: Plugins are serialized as JSON files for sharing and backup.
- **Install/Uninstall**: After configuration changes, the plugin must be saved and reinstalled.

## Integration Points

Plugins connect to the rest of the Viewtinet platform:
- [Inventory](../configuracion/inventory-management.md) provisions hosts for SNMP and ICMP-based plugins.
- The [Schema stage](plugin-schema.md) prepares data for [ViewtiSight](../productos/viewtisight-overview.md) metrics.
- [Producers](../integraciones/data-producers.md) in the Load stage route data to the Viewtinet TSDB or external destinations.
