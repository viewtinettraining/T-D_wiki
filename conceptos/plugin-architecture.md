---
tags: [concepto, plugin, vs-data-broker]
tipo: concepto
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Plugin Architecture

In the [[vs-data-broker-overview|Visual Smart Data Broker (VSDB)]], a **plugin** is the fundamental organizational unit. It acts as a mandatory container for one or more [[etl-pipeline|ETL pipelines]]. No pipeline can exist outside of a plugin — the plugin provides the framework where pipelines are defined, documented, and linked to dashboards, alarms, and reports.

## What a Plugin Contains

A plugin is composed of:

- **One or more Pipelines** — Each pipeline executes the full ETL cycle: Extract, Transform, Load, and Schema stages.
- **Name** — A descriptive label (e.g., "Fortinet Network Monitoring Template").
- **Category** — Classification into [[plugin-categories|a named category]] such as SNMP, Syslog, SSH, Network, WMI, etc.
- **Description** — A human-readable summary of what the plugin collects.
- **Dependencies** — Modules required for the plugin to function.
- **Image** — An optional JPG/PNG image to visually identify the plugin.

## Two Plugin Types

There are two types of plugins in VSDB:

1. **[[plugin-template|Plugin Templates]]** — Pre-built integrations distributed by Viewtinet. These come with Extract, Transform, Load stages and dashboards already configured. In most cases, only the target IP address is needed to deploy them.

2. **[[customized-plugin|Customized Plugins]]** — Created from scratch using the Plugin Creator wizard when a data source is not available in the template library, or when custom fields are required beyond what a template provides.

## Plugin Lifecycle

- **Create**: Use the "Create New Plugin" button in the [[vs-data-broker-overview|VSDB]] GUI.
- **Edit**: Each pipeline stage can be modified individually via the Edit button.
- **Clone**: An exact copy can be created without affecting existing installations.
- **Export/Import**: Plugins are serialized as JSON files for sharing and backup.
- **Install/Uninstall**: After configuration changes, the plugin must be saved and reinstalled.

## Integration Points

Plugins connect to the rest of the Viewtinet platform:
- [[inventory-management|Inventory]] provisions hosts for SNMP and ICMP-based plugins.
- The [[plugin-schema|Schema stage]] prepares data for [[viewtisight-overview|ViewtiSight]] metrics.
- [[data-producers|Producers]] in the Load stage route data to the Viewtinet TSDB or external destinations.
