---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'VS Data Broker Overview'
id: OXT-JZH-WG6-09W
slug: vs-data-broker-overview
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# VS Data Broker Overview

The **Visual Smart Data Broker (VSDB)** is a core component of the Viewtinet platform, serving as its **ETL engine**. It provides a visual, no-code interface for defining Extract, Transform, and Load pipelines that collect data from heterogeneous IT, OT, and IoT environments and deliver it to the appropriate Viewtinet modules for storage, dashboards, and alerting.

## Purpose and Role

VSDB is the point where raw, disparate inputs from network devices, servers, APIs, and sensors are converted into consistent, high-quality telemetry. Administrators configure [ETL pipelines](../conceptos/etl-pipeline.md) visually without writing complex code. It is accessible from within [Viewtimanager Overview](viewtimanager-overview.md) via the "V.S. Data Broker" menu in the left navigation panel.

## Architecture

All ETL logic in VSDB is organized into **[plugins](../conceptos/plugin-architecture.md)**. A plugin is the mandatory container for one or more pipelines — it is not possible to create a pipeline without associating it to a plugin. Each plugin maps to a category (see [Plugin Categories](../conceptos/plugin-categories.md)) and may include predefined dashboards and alarm associations.

Two types of plugins exist:
- **[Plugin Templates](../conceptos/plugin-template.md)** — Pre-configured integrations distributed by Viewtinet, covering many vendors and protocols.
- **[Customized Plugins](../conceptos/customized-plugin.md)** — User-created plugins built from scratch using the plugin creator wizard.

## ETL Cycle

The [ETL pipeline](../conceptos/etl-pipeline.md) consists of three main stages:

1. **Extract** — Protocol connectors acquire data from sources. Supported connectors include [SNMP](../integraciones/snmp-extractor.md), [ICMP](../integraciones/icmp-extractor.md), [NetFlow](../integraciones/netflow-extractor.md), [sFlow](../integraciones/sflow-extractor.md), [Syslog](../integraciones/syslog-extractor.md), [SSH](../integraciones/ssh-extractor.md), [CSV](../integraciones/csv-extractor.md), [MongoDB](../integraciones/mongodb-extractor.md), [Python Task](../integraciones/python-task-extractor.md), [Ethernet Streamer](../integraciones/ethernet-streamer.md), [Command Executor](../integraciones/command-executor.md), and more.
2. **Transform** — Grid Handlers parse, normalize, enrich, and apply math operations to the raw data. The [Column Constant Adder](../integraciones/column-constant-adder.md) is one example handler.
3. **Load** — [Producers](../integraciones/data-producers.md) deliver processed data to the Viewtinet Time Series Database (TSDB) by default, or export to Syslog, SCP, CSV, or Kafka.

## Key Features

- Visual ETL pipeline builder with no coding required
- Multi-source extraction via diverse protocol connectors
- Transformation and enrichment through Grid Handlers
- Retention policies and governance controls
- Horizontal scalability for high-volume data streams
- Operational monitoring with counters and logs

## Plugin Management

Plugins can be **edited**, **cloned**, **exported** (as JSON), and **imported** — enabling sharing with the Viewtinet support team and reuse across environments. Plugin provisioning for SNMP and ICMP templates is integrated with [Inventory Management](../configuracion/inventory-management.md).

The [schema stage](../conceptos/plugin-schema.md) within each pipeline prepares data for use in [ViewtiSight](viewtisight-overview.md) metrics and dimensions.
