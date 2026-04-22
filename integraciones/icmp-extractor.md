---
tags: [integracion, icmp, extractor, vs-data-broker]
tipo: tecnica
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ICMP Extractor

The **ICMP Connector** enables the [[vs-data-broker-overview|Visual Smart Data Broker (VSDB)]] to perform network reachability and latency checks using ping (ICMP echo requests). It monitors availability and packet loss across servers, routers, switches, and any IP-enabled device.

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
- **Mass provisioning via [[inventory-management|Inventory]]** (recommended for large environments)
- **Manual entry** using the "Add Host" button

The [[plugin-categories|ICMP category]] in the VSDB GUI groups all ICMP-based plugins together for easy filtering.

## Related Pages

- [[snmp-extractor]] — Alternative for device metrics beyond reachability
- [[etl-pipeline]] — Full ETL pipeline context
- [[inventory-management]] — Mass host provisioning
- [[plugin-categories]] — ICMP is a dedicated plugin category
- [[vs-data-broker-overview]] — VSDB product overview
