---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'VS Data Broker — Source Section Index'
id: Z72-4YK-DSE-QOF
slug: vs-data-broker-section
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# VS Data Broker — Source Section Index

This page catalogs all source files processed for the [VS Data Broker](../productos/vs-data-broker-overview.md) wiki section. It covers the full ETL pipeline documentation: overview, [plugin architecture](../conceptos/plugin-architecture.md), all [ETL](../conceptos/etl-pipeline.md) extractors, transformers, and producers.

## Overview and GUI

- `intro.md` — Introduction to [VSDB](../productos/vs-data-broker-overview.md), purpose, key features, and ETL cycle diagram
- `gui-overview.md` — GUI location in [Viewtimanager Overview](../productos/viewtimanager-overview.md), panel layout, plugin cards, action buttons

## Plugin Concepts

- `what-is-a-plugin.md` — Defines the [plugin](../conceptos/plugin-architecture.md) container: pipeline stages (Extract, Transform, Load, Schema, Dashboards), metadata fields
- `what-is-a-plugin-template.md` — Describes [plugin templates](../conceptos/plugin-template.md) distributed by Viewtinet, covers provisioning via [Inventory Management](../configuracion/inventory-management.md)
- `what-is-a-customized-plugin.md` — Defines [customized plugins](../conceptos/customized-plugin.md) created from scratch or to extend an existing template
- `categories.md` — [Plugin category](../conceptos/plugin-categories.md) classification: CDR, ICMP, Network, Optimization, SNMP, SSH, Sflow, Syslog, Viewtinet, WMI
- `plugin-editing.md` — How to edit plugin stages; reminder to save and reinstall
- `clone.md` — Cloning a plugin to create an exact copy without affecting existing datasets
- `export-and-import.md` — Exporting plugins as JSON and importing them; used for team sharing and support

## Custom Plugin Creation

- `creating-a-custom-plugin/about.md` — Outline of 6-step custom plugin creation process
- `creating-a-custom-plugin/create.md` — Step-by-step wizard: name, description, category, dependencies, image
- `creating-a-custom-plugin/schema/index.md` — [Schema stage](../conceptos/plugin-schema.md) index (empty in source; schema is defined in pipeline)

## Extract Connectors

- `extract/snmp.md` — [SNMP Connector](../integraciones/snmp-extractor.md): frequency types, host partitioning, SNMP credentials
- `extract/snmp-trap-connector.md` — [SNMP Trap Connector](../integraciones/snmp-trap-connector.md): managed by Viewtinet support only
- `extract/netflow.md` — [NetFlow Connector](../integraciones/netflow-extractor.md): works with [Ethernet Streamer](../integraciones/ethernet-streamer.md), versions 5/9/IPFIX
- `extract/sflow.md` — [sFlow Connector](../integraciones/sflow-extractor.md): works with [Ethernet Streamer](../integraciones/ethernet-streamer.md), sFlow v5
- `extract/syslog.md` — [Syslog Connector](../integraciones/syslog-extractor.md): reads dumps from [Ethernet Streamer](../integraciones/ethernet-streamer.md), multi-thread
- `extract/ssh.md` — [SSH Query Connector](../integraciones/ssh-extractor.md): remote metrics via SSH, query types (cpu, disk, memory, network, cmd)
- `extract/wmi.md` — [WMI Connector](../integraciones/wmi-extractor.md): deprecated after Microsoft March 2013 patch; use [Windows Remote Management](../integraciones/windows-remote-management.md) instead
- `extract/windows-remote-management/intro.md` — [WinRM Connector](../integraciones/windows-remote-management.md) introduction
- `extract/windows-remote-management/prerequisites.md` — WinRM prerequisites: PowerShell setup, certificates, firewall rules
- `extract/csv.md` — [CSV Connector](../integraciones/csv-extractor.md): file ingestion, configurable separator, VoIP CDR/CMR use cases
- `extract/mongodb.md` — [MongoDB Connector](../integraciones/mongodb-extractor.md): URI-based, incremental with `.tf` tracking file
- `extract/icmp.md` — [ICMP Connector](../integraciones/icmp-extractor.md): ping health checks, batch size, packet loss calculation
- `extract/python-task.md` — [Python Task Connector](../integraciones/python-task-extractor.md): custom scripts, DataWrapper template, mandatory `timestamp` field
- `extract/ethernet-streamer.md` — [Ethernet Streamer](../integraciones/ethernet-streamer.md): continuous listener for NetFlow/Syslog, tcpdump filters
- `extract/flow-emitter.md` — [Flow Emitter Connector](../integraciones/flow-emitter.md): internal DPI data from [Viewtimon Overview](../productos/viewtimon-overview.md)
- `extract/file-list.md` — File List Connector: scheduled file mover, pairs with SCP Producer
- `extract/command-executor.md` — [Command Executor Connector](../integraciones/command-executor.md): bash scripts or CLI commands as data sources

## Transform

- `transform/column-constant-adder.md` — [Column Constant Adder](../integraciones/column-constant-adder.md) grid handler: adds a constant value or text to a column

## Load

- `load/producers.md` — [Producers](../integraciones/data-producers.md): Aggregator, CSV Writer, Rotational CSV Writer, Syslog Producer, SCP Producer, ViewtinetDB Producer, Kafka Producer
