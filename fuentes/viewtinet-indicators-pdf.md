---
tags: [fuentes, indicadores, metricas, kpi, viewtisight]
tipo: fuente
fuentes: ["Viewtinet Indicators"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Viewtinet Indicators PDF — Source Summary

This page summarizes the Viewtinet Indicators document, which catalogs the key performance indicators (KPIs), metrics, and dimensions available within the [[viewtinet-platform-overview|Viewtinet platform]]. It serves as a reference for teams configuring dashboards, alarms, and metrics in [[viewtisight-features|ViewtiSight]].

## Purpose of the Document

The Indicators document defines the measurable data points that Viewtinet collects, computes, and exposes through its analytics layer. These indicators are the foundation for:

- Building [[viewtisight-features|Dashboard Composer]] widgets
- Defining rules in the [[alarms-system|alarms system]]
- Creating KPIs in the Metrics Composer
- Querying data via the [[rest-api|REST API]]

## Indicator Categories

Indicators are organized by the module or protocol that generates them:

### Network Traffic Indicators (ViewtiMon / ViewtiLog)
- **Throughput** — bytes in/out per interface, per application, per protocol
- **Packet counts** — unicast, multicast, broadcast, and error packets
- **Flow metrics** — active flows, new flows per second, top talkers
- **Application recognition** — traffic volume per DPI-classified application

### Quality of Experience (QoE)
- **Latency** — round-trip time per flow or destination
- **Jitter** — latency variation for real-time traffic (VoIP, video)
- **Packet loss** — percentage of dropped packets per session
- **MOS score** — Mean Opinion Score for voice quality assessment

### SNMP Device Indicators
- Interface utilization (in/out bps, errors, discards)
- CPU and memory utilization per device
- Custom OID-based metrics via [[snmp-extractor|SNMP extractor]] configuration

### Syslog and Log Indicators
- Event counts per severity, per source, per time window
- Protocol distribution from [[netflow-extractor|NetFlow]] and [[sflow-extractor|sFlow]] data
- CDR metrics for telephony environments

## Dimensions

Each indicator can be sliced by one or more **dimensions** — metadata fields that allow grouping and filtering:

- Device / hostname / IP address
- Interface name or index
- Application / protocol
- Direction (inbound / outbound)
- Location / site
- [[tenants|Tenant]] identifier (for multi-tenant deployments)

Dimensions are defined in the [[plugin-architecture|plugin schema stage]] and become available in [[viewtisight-features|ViewtiSight]] and the [[rest-api|REST API]] query engine.

## Usage in ViewtiSight

Indicators documented in this PDF map directly to the dataset fields visible in the [[viewtisight-features|QueryBuilder]]. When configuring a [[viewtisight-features|Metrics Composer]] metric or an [[alarms-system|alarm rule]], the list of available fields comes from this indicator catalog.

Indicator data is stored in Viewticore's time-series database and is accessible through [[data-sources-integration|plugin datasets]] and the REST API.

## Related Pages

- [[viewtisight-features]] — how indicators are used in dashboards and metrics
- [[alarms-system]] — using indicators to define alarm thresholds
- [[data-sources-integration]] — how indicators are produced by plugins
- [[snmp-extractor]], [[netflow-extractor]], [[sflow-extractor]] — protocol-specific indicator sources
- [[rest-api]] — programmatic access to indicator data
