---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Ethernet Streamer'
id: 1X8-2GN-A84-2EU
slug: ethernet-streamer
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Ethernet Streamer

The Ethernet Streamer Connector is a continuous listener in the [VS Data Broker](../productos/vs-data-broker-overview.md) Extract stage. Unlike scheduled connectors such as [Snmp Extractor](snmp-extractor.md), [Icmp Extractor](icmp-extractor.md), or [Csv Extractor](csv-extractor.md), the Ethernet Streamer runs constantly without interruption, ensuring no incoming packets are missed.

## Purpose

The connector listens on a selected network interface for traffic carrying protocols such as Syslog, NetFlow, jFlow, NetStream, and sFlow. It captures all matching packets in raw binary format and writes them to disk on the Viewtilog server.

Crucially, the Ethernet Streamer does **not** decode or parse the captured traffic. Its role is purely to record raw data reliably. Decoding is delegated to specialized connectors — such as [Syslog Extractor](syslog-extractor.md) and [Netflow Extractor](netflow-extractor.md) — which read those binary dumps in later stages of the [Etl Pipeline](../conceptos/etl-pipeline.md).

## Key Features

- Operates as a real-time traffic listener, never scheduled.
- Captures packets in binary format to a configurable directory on disk.
- Supports tcpdump-syntax filters to restrict capture by protocol, port, or source/destination IP.
- Multiple downstream connectors can consume the same binary dump, enabling reuse.
- Does not decode or transform data — that is handled by the Transform stage.

## Using Filters

Filters follow tcpdump syntax. Examples:

```bash
# Capture all NetFlow (UDP port 2055)
port 2055

# Capture Syslog traffic (UDP port 514)
port 514

# Capture NetFlow from a specific host
host 10.10.10.1 and port 2055

# Capture NetFlow from multiple hosts
(host 10.10.10.1 or host 10.10.10.2 or host 10.10.10.3) and port 2055
```

Filters reduce disk usage and improve performance by storing only relevant traffic.

## Configuration Steps

1. In the **Editing Extract Stage** window within the [plugin editor](../conceptos/plugin-architecture.md), open the **Connector/Streamer Type** list and select **Ethernet Streamer**.
2. Enter a unique **Pipeline Name** (e.g., `my_ethernet_streamer_pipeline`).
3. In **Streamer Config**, select the **network interface** to listen on (e.g., `enp1s0f3`).
4. Optionally, enter a **Filter** expression in tcpdump syntax.
5. Click **Confirm** to activate the pipeline.

Once confirmed, the pipeline starts immediately and runs continuously.

## Pipeline Role

The Ethernet Streamer sits at the beginning of the [Etl Pipeline](../conceptos/etl-pipeline.md) for flow and log-based data:

```
Ethernet Streamer → Binary Files on Disk → Syslog/NetFlow Connector → Transform → Load
```

This design decouples raw capture from protocol decoding, allowing the same binary data to be processed independently by [Syslog Extractor](syslog-extractor.md), [Netflow Extractor](netflow-extractor.md), or [Sflow Extractor](sflow-extractor.md) connectors.

See [Customized Plugin](../conceptos/customized-plugin.md) for how to assemble a complete plugin using this connector, and [Data Producers](data-producers.md) for available output targets in the Load stage.
