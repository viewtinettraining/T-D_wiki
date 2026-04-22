---
title: "SNMP Trap Connector"
description: "The SNMP Trap Connector appears as one of the available connectors in the Extract stage of the ETL pipeline within the Visual Smart Data Broker (VSDB). Howev..."
keywords: "integracion, snmp, trap, vs-data-broker"
---

# SNMP Trap Connector

The **SNMP Trap Connector** appears as one of the available connectors in the Extract stage of the [ETL pipeline](../conceptos/etl-pipeline.md) within the [Visual Smart Data Broker (VSDB)](../productos/vs-data-broker-overview.md). However, it is **not intended for direct configuration or use by end users**.

## Important Disclaimer

The implementation of this connector depends on advanced configurations and internal processes managed exclusively by Viewtinet. It cannot be set up or operated directly from the user interface without support assistance.

If your project requires SNMP Trap integration, contact **Viewtinet Support** or your account representative.

## How SNMP Traps Differ from Polling

Unlike the [SNMP Connector](snmp-extractor.md) which actively polls devices at scheduled intervals, SNMP Traps are **event-driven notifications** sent by devices to the management platform. This passive listening model requires different internal infrastructure managed by Viewtinet.

## Relationship to Other Connectors

The SNMP Trap Connector fits alongside the [SNMP Connector](snmp-extractor.md) in the broader [SNMP category](../conceptos/plugin-categories.md). Both ultimately populate the [ETL pipeline](../conceptos/etl-pipeline.md), but through fundamentally different acquisition mechanisms.

## Related Pages

- [Snmp Extractor](snmp-extractor.md) — Active SNMP polling connector
- [Etl Pipeline](../conceptos/etl-pipeline.md) — ETL pipeline context
- [Plugin Architecture](../conceptos/plugin-architecture.md) — Plugin structure
- [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) — VSDB product overview
- [Ethernet Streamer](ethernet-streamer.md) — Another passive-capture connector (for flow/log protocols)
