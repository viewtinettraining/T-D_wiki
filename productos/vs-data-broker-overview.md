---
tags: [producto, vs-data-broker, etl]
tipo: tecnica
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# VS Data Broker Overview

The **Visual Smart Data Broker (VSDB)** is a core component of the Viewtinet platform, serving as its **ETL engine**. It provides a visual, no-code interface for defining Extract, Transform, and Load pipelines that collect data from heterogeneous IT, OT, and IoT environments and deliver it to the appropriate Viewtinet modules for storage, dashboards, and alerting.

## Purpose and Role

VSDB is the point where raw, disparate inputs from network devices, servers, APIs, and sensors are converted into consistent, high-quality telemetry. Administrators configure [[etl-pipeline|ETL pipelines]] visually without writing complex code. It is accessible from within [[viewtimanager-overview]] via the "V.S. Data Broker" menu in the left navigation panel.

## Architecture

All ETL logic in VSDB is organized into **[[plugin-architecture|plugins]]**. A plugin is the mandatory container for one or more pipelines — it is not possible to create a pipeline without associating it to a plugin. Each plugin maps to a category (see [[plugin-categories]]) and may include predefined dashboards and alarm associations.

Two types of plugins exist:
- **[[plugin-template|Plugin Templates]]** — Pre-configured integrations distributed by Viewtinet, covering many vendors and protocols.
- **[[customized-plugin|Customized Plugins]]** — User-created plugins built from scratch using the plugin creator wizard.

## ETL Cycle

The [[etl-pipeline|ETL pipeline]] consists of three main stages:

1. **Extract** — Protocol connectors acquire data from sources. Supported connectors include [[snmp-extractor|SNMP]], [[icmp-extractor|ICMP]], [[netflow-extractor|NetFlow]], [[sflow-extractor|sFlow]], [[syslog-extractor|Syslog]], [[ssh-extractor|SSH]], [[csv-extractor|CSV]], [[mongodb-extractor|MongoDB]], [[python-task-extractor|Python Task]], [[ethernet-streamer|Ethernet Streamer]], [[command-executor|Command Executor]], and more.
2. **Transform** — Grid Handlers parse, normalize, enrich, and apply math operations to the raw data. The [[column-constant-adder|Column Constant Adder]] is one example handler.
3. **Load** — [[data-producers|Producers]] deliver processed data to the Viewtinet Time Series Database (TSDB) by default, or export to Syslog, SCP, CSV, or Kafka.

## Key Features

- Visual ETL pipeline builder with no coding required
- Multi-source extraction via diverse protocol connectors
- Transformation and enrichment through Grid Handlers
- Retention policies and governance controls
- Horizontal scalability for high-volume data streams
- Operational monitoring with counters and logs

## Plugin Management

Plugins can be **edited**, **cloned**, **exported** (as JSON), and **imported** — enabling sharing with the Viewtinet support team and reuse across environments. Plugin provisioning for SNMP and ICMP templates is integrated with [[inventory-management]].

The [[plugin-schema|schema stage]] within each pipeline prepares data for use in [[viewtisight-overview|ViewtiSight]] metrics and dimensions.
