---
tags: [integraciones, vsdb, extractor]
tipo: tecnica
fuentes: ["ethernet-streamer"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Ethernet Streamer

The Ethernet Streamer Connector is a continuous listener in the [[vs-data-broker-overview|VS Data Broker]] Extract stage. Unlike scheduled connectors such as [[snmp-extractor]], [[icmp-extractor]], or [[csv-extractor]], the Ethernet Streamer runs constantly without interruption, ensuring no incoming packets are missed.

## Purpose

The connector listens on a selected network interface for traffic carrying protocols such as Syslog, NetFlow, jFlow, NetStream, and sFlow. It captures all matching packets in raw binary format and writes them to disk on the Viewtilog server.

Crucially, the Ethernet Streamer does **not** decode or parse the captured traffic. Its role is purely to record raw data reliably. Decoding is delegated to specialized connectors — such as [[syslog-extractor]] and [[netflow-extractor]] — which read those binary dumps in later stages of the [[etl-pipeline]].

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

1. In the **Editing Extract Stage** window within the [[plugin-architecture|plugin editor]], open the **Connector/Streamer Type** list and select **Ethernet Streamer**.
2. Enter a unique **Pipeline Name** (e.g., `my_ethernet_streamer_pipeline`).
3. In **Streamer Config**, select the **network interface** to listen on (e.g., `enp1s0f3`).
4. Optionally, enter a **Filter** expression in tcpdump syntax.
5. Click **Confirm** to activate the pipeline.

Once confirmed, the pipeline starts immediately and runs continuously.

## Pipeline Role

The Ethernet Streamer sits at the beginning of the [[etl-pipeline]] for flow and log-based data:

```
Ethernet Streamer → Binary Files on Disk → Syslog/NetFlow Connector → Transform → Load
```

This design decouples raw capture from protocol decoding, allowing the same binary data to be processed independently by [[syslog-extractor]], [[netflow-extractor]], or [[sflow-extractor]] connectors.

See [[customized-plugin]] for how to assemble a complete plugin using this connector, and [[data-producers]] for available output targets in the Load stage.
