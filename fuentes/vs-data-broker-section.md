---
tags: [fuente, vs-data-broker]
tipo: fuente
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# VS Data Broker — Source Section Index

This page catalogs all source files processed for the [[vs-data-broker-overview|VS Data Broker]] wiki section. It covers the full ETL pipeline documentation: overview, [[plugin-architecture|plugin architecture]], all [[etl-pipeline|ETL]] extractors, transformers, and producers.

## Overview and GUI

- `intro.md` — Introduction to [[vs-data-broker-overview|VSDB]], purpose, key features, and ETL cycle diagram
- `gui-overview.md` — GUI location in [[viewtimanager-overview]], panel layout, plugin cards, action buttons

## Plugin Concepts

- `what-is-a-plugin.md` — Defines the [[plugin-architecture|plugin]] container: pipeline stages (Extract, Transform, Load, Schema, Dashboards), metadata fields
- `what-is-a-plugin-template.md` — Describes [[plugin-template|plugin templates]] distributed by Viewtinet, covers provisioning via [[inventory-management]]
- `what-is-a-customized-plugin.md` — Defines [[customized-plugin|customized plugins]] created from scratch or to extend an existing template
- `categories.md` — [[plugin-categories|Plugin category]] classification: CDR, ICMP, Network, Optimization, SNMP, SSH, Sflow, Syslog, Viewtinet, WMI
- `plugin-editing.md` — How to edit plugin stages; reminder to save and reinstall
- `clone.md` — Cloning a plugin to create an exact copy without affecting existing datasets
- `export-and-import.md` — Exporting plugins as JSON and importing them; used for team sharing and support

## Custom Plugin Creation

- `creating-a-custom-plugin/about.md` — Outline of 6-step custom plugin creation process
- `creating-a-custom-plugin/create.md` — Step-by-step wizard: name, description, category, dependencies, image
- `creating-a-custom-plugin/schema/index.md` — [[plugin-schema|Schema stage]] index (empty in source; schema is defined in pipeline)

## Extract Connectors

- `extract/snmp.md` — [[snmp-extractor|SNMP Connector]]: frequency types, host partitioning, SNMP credentials
- `extract/snmp-trap-connector.md` — [[snmp-trap-connector|SNMP Trap Connector]]: managed by Viewtinet support only
- `extract/netflow.md` — [[netflow-extractor|NetFlow Connector]]: works with [[ethernet-streamer]], versions 5/9/IPFIX
- `extract/sflow.md` — [[sflow-extractor|sFlow Connector]]: works with [[ethernet-streamer]], sFlow v5
- `extract/syslog.md` — [[syslog-extractor|Syslog Connector]]: reads dumps from [[ethernet-streamer]], multi-thread
- `extract/ssh.md` — [[ssh-extractor|SSH Query Connector]]: remote metrics via SSH, query types (cpu, disk, memory, network, cmd)
- `extract/wmi.md` — [[wmi-extractor|WMI Connector]]: deprecated after Microsoft March 2013 patch; use [[windows-remote-management]] instead
- `extract/windows-remote-management/intro.md` — [[windows-remote-management|WinRM Connector]] introduction
- `extract/windows-remote-management/prerequisites.md` — WinRM prerequisites: PowerShell setup, certificates, firewall rules
- `extract/csv.md` — [[csv-extractor|CSV Connector]]: file ingestion, configurable separator, VoIP CDR/CMR use cases
- `extract/mongodb.md` — [[mongodb-extractor|MongoDB Connector]]: URI-based, incremental with `.tf` tracking file
- `extract/icmp.md` — [[icmp-extractor|ICMP Connector]]: ping health checks, batch size, packet loss calculation
- `extract/python-task.md` — [[python-task-extractor|Python Task Connector]]: custom scripts, DataWrapper template, mandatory `timestamp` field
- `extract/ethernet-streamer.md` — [[ethernet-streamer|Ethernet Streamer]]: continuous listener for NetFlow/Syslog, tcpdump filters
- `extract/flow-emitter.md` — [[flow-emitter|Flow Emitter Connector]]: internal DPI data from [[viewtimon-overview]]
- `extract/file-list.md` — File List Connector: scheduled file mover, pairs with SCP Producer
- `extract/command-executor.md` — [[command-executor|Command Executor Connector]]: bash scripts or CLI commands as data sources

## Transform

- `transform/column-constant-adder.md` — [[column-constant-adder|Column Constant Adder]] grid handler: adds a constant value or text to a column

## Load

- `load/producers.md` — [[data-producers|Producers]]: Aggregator, CSV Writer, Rotational CSV Writer, Syslog Producer, SCP Producer, ViewtinetDB Producer, Kafka Producer
