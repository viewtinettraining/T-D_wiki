---
tags: [integracion, snmp, trap, vs-data-broker]
tipo: tecnica
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# SNMP Trap Connector

The **SNMP Trap Connector** appears as one of the available connectors in the Extract stage of the [[etl-pipeline|ETL pipeline]] within the [[vs-data-broker-overview|Visual Smart Data Broker (VSDB)]]. However, it is **not intended for direct configuration or use by end users**.

## Important Disclaimer

The implementation of this connector depends on advanced configurations and internal processes managed exclusively by Viewtinet. It cannot be set up or operated directly from the user interface without support assistance.

If your project requires SNMP Trap integration, contact **Viewtinet Support** or your account representative.

## How SNMP Traps Differ from Polling

Unlike the [[snmp-extractor|SNMP Connector]] which actively polls devices at scheduled intervals, SNMP Traps are **event-driven notifications** sent by devices to the management platform. This passive listening model requires different internal infrastructure managed by Viewtinet.

## Relationship to Other Connectors

The SNMP Trap Connector fits alongside the [[snmp-extractor|SNMP Connector]] in the broader [[plugin-categories|SNMP category]]. Both ultimately populate the [[etl-pipeline|ETL pipeline]], but through fundamentally different acquisition mechanisms.

## Related Pages

- [[snmp-extractor]] — Active SNMP polling connector
- [[etl-pipeline]] — ETL pipeline context
- [[plugin-architecture]] — Plugin structure
- [[vs-data-broker-overview]] — VSDB product overview
- [[ethernet-streamer]] — Another passive-capture connector (for flow/log protocols)
