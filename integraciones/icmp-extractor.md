---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'ICMP Extractor'
id: CRZ-O8U-QVP-GI5
slug: icmp-extractor
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# ICMP Extractor

The **ICMP Connector** enables the [Visual Smart Data Broker (VSDB)](../productos/vs-data-broker-overview.md) to perform network reachability and latency checks using ping (ICMP echo requests). It monitors availability and packet loss across servers, routers, switches, and any IP-enabled device.

## Configuration Parameters

| Parameter | Description |
|---|---|
| **Frequency Type** | `Periodic` (every X seconds) or `Scheduled` (cron expression) |
| **Number of Executions** | `-1` for indefinite; positive integer for fixed runs |
| **Session** | Mandatory string parameter to track execution internally |
| **Ping Count** | Number of echo requests sent per host per cycle |
| **Ping Timeout** | Max waiting time (seconds) for each echo reply before declaring loss |
| **Host Batch Size** | Number of hosts pinged simultaneously per batch |

## Packet Loss Calculation

Packet loss percentage is calculated as:

```
Lost packets / Ping Count × 100
```

- A host is declared **down** only when **all** echo requests fail.
- Example: `Ping Count = 5`, 1 lost → 20% packet loss.

## Host Batching

`Host Batch Size` controls how many hosts are pinged in parallel. For example, with 100 hosts and `Host Batch Size = 50`, the system creates 2 parallel pipelines, each handling 50 hosts. This prevents overloading the network with simultaneous pings.

## Host Provisioning

Hosts can be added in two ways:
- **Mass provisioning via [Inventory](../configuracion/inventory-management.md)** (recommended for large environments)
- **Manual entry** using the "Add Host" button

The [ICMP category](../conceptos/plugin-categories.md) in the VSDB GUI groups all ICMP-based plugins together for easy filtering.

## Related Pages

- [Snmp Extractor](snmp-extractor.md) — Alternative for device metrics beyond reachability
- [Etl Pipeline](../conceptos/etl-pipeline.md) — Full ETL pipeline context
- [Inventory Management](../configuracion/inventory-management.md) — Mass host provisioning
- [Plugin Categories](../conceptos/plugin-categories.md) — ICMP is a dedicated plugin category
- [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) — VSDB product overview
