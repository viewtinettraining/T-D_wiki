---
tags: [integracion, snmp, extractor, vs-data-broker]
tipo: tecnica
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# SNMP Extractor

The **SNMP Connector** is one of the most widely used connectors in the [[vs-data-broker-overview|Visual Smart Data Broker (VSDB)]]. It polls network devices, servers, and any SNMP-capable system to extract metrics via OIDs. It operates in the Extract stage of the [[etl-pipeline|ETL pipeline]] within a [[plugin-architecture|plugin]].

## Configuration Parameters

| Parameter | Description |
|---|---|
| **Frequency Type** | `Periodic` (runs every X seconds) or `Scheduled` (cron expression) |
| **Refresh Time (secs)** | Interval between executions (Periodic mode only) |
| **Number of Executions** | `-1` for indefinite; positive integer for fixed runs |
| **Session** | Mandatory string; uniquely identifies the execution session |
| **hostPartitionSize** | Max hosts per polling batch (default: 0 = no batching) |
| **partitionDelay (secs)** | Wait time between batches (default: 30 seconds) |

## SNMP Credentials

The connector requires default credentials applied to all hosts:
- **SNMP Version**: v1, v2c, or v3
- **Community**: for SNMP v1/v2c
- **Authentication and Privacy fields**: for SNMP v3

Credentials can be overridden per host when needed.

## Host Partitioning

When polling large numbers of devices, `hostPartitionSize` and `partitionDelay` divide the workload into manageable batches. For example, with 100 devices, `hostPartitionSize=20` and `partitionDelay=10` creates 5 groups of 20, each polled 10 seconds apart.

**Warning**: If the total polling time exceeds the configured refresh interval, executions may overlap and cause inaccurate timestamps.

## Host Provisioning

Hosts are typically provisioned through the [[inventory-management|Inventory module]] for large-scale deployments. Individual hosts can also be added manually via the "Add Host" button with a specific OID Group.

## Related Pages

- [[etl-pipeline]] — Full pipeline context
- [[plugin-architecture]] — Plugin as container
- [[plugin-categories]] — SNMP is a dedicated category
- [[snmp-trap-connector]] — Separate connector for trap-based integration
- [[inventory-management]] — Mass host provisioning
