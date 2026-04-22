---
title: "SNMP Extractor"
description: "The SNMP Connector is one of the most widely used connectors in the Visual Smart Data Broker (VSDB). It polls network devices, servers, and any SNMP-capable ..."
keywords: "integracion, snmp, extractor, vs-data-broker"
---

# SNMP Extractor

The **SNMP Connector** is one of the most widely used connectors in the [Visual Smart Data Broker (VSDB)](../productos/vs-data-broker-overview.md). It polls network devices, servers, and any SNMP-capable system to extract metrics via OIDs. It operates in the Extract stage of the [ETL pipeline](../conceptos/etl-pipeline.md) within a [plugin](../conceptos/plugin-architecture.md).

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

Hosts are typically provisioned through the [Inventory module](../configuracion/inventory-management.md) for large-scale deployments. Individual hosts can also be added manually via the "Add Host" button with a specific OID Group.

## Related Pages

- [Etl Pipeline](../conceptos/etl-pipeline.md) — Full pipeline context
- [Plugin Architecture](../conceptos/plugin-architecture.md) — Plugin as container
- [Plugin Categories](../conceptos/plugin-categories.md) — SNMP is a dedicated category
- [Snmp Trap Connector](snmp-trap-connector.md) — Separate connector for trap-based integration
- [Inventory Management](../configuracion/inventory-management.md) — Mass host provisioning
