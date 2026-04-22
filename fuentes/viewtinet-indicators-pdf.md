---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Viewtinet Indicators PDF — Source Summary'
id: BKM-RC6-4I6-YN3
slug: viewtinet-indicators-pdf
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Viewtinet Indicators PDF — Source Summary

This page summarizes the Viewtinet Indicators document, which catalogs the key performance indicators (KPIs), metrics, and dimensions available within the [Viewtinet platform](../productos/viewtinet-platform-overview.md). It serves as a reference for teams configuring dashboards, alarms, and metrics in [ViewtiSight](../productos/viewtisight-features.md).

## Purpose of the Document

The Indicators document defines the measurable data points that Viewtinet collects, computes, and exposes through its analytics layer. These indicators are the foundation for:

- Building [Dashboard Composer](../productos/viewtisight-features.md) widgets
- Defining rules in the [alarms system](../conceptos/alarms-system.md)
- Creating KPIs in the Metrics Composer
- Querying data via the [REST API](../productos/rest-api.md)

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
- Custom OID-based metrics via [SNMP extractor](../integraciones/snmp-extractor.md) configuration

### Syslog and Log Indicators
- Event counts per severity, per source, per time window
- Protocol distribution from [NetFlow](../integraciones/netflow-extractor.md) and [sFlow](../integraciones/sflow-extractor.md) data
- CDR metrics for telephony environments

## Dimensions

Each indicator can be sliced by one or more **dimensions** — metadata fields that allow grouping and filtering:

- Device / hostname / IP address
- Interface name or index
- Application / protocol
- Direction (inbound / outbound)
- Location / site
- [Tenant](../configuracion/tenants.md) identifier (for multi-tenant deployments)

Dimensions are defined in the [plugin schema stage](../conceptos/plugin-architecture.md) and become available in [ViewtiSight](../productos/viewtisight-features.md) and the [REST API](../productos/rest-api.md) query engine.

## Usage in ViewtiSight

Indicators documented in this PDF map directly to the dataset fields visible in the [QueryBuilder](../productos/viewtisight-features.md). When configuring a [Metrics Composer](../productos/viewtisight-features.md) metric or an [alarm rule](../conceptos/alarms-system.md), the list of available fields comes from this indicator catalog.

Indicator data is stored in Viewticore's time-series database and is accessible through [plugin datasets](../conceptos/data-sources-integration.md) and the REST API.

## Related Pages

- [Viewtisight Features](../productos/viewtisight-features.md) — how indicators are used in dashboards and metrics
- [Alarms System](../conceptos/alarms-system.md) — using indicators to define alarm thresholds
- [Data Sources Integration](../conceptos/data-sources-integration.md) — how indicators are produced by plugins
- [Snmp Extractor](../integraciones/snmp-extractor.md), [Netflow Extractor](../integraciones/netflow-extractor.md), [Sflow Extractor](../integraciones/sflow-extractor.md) — protocol-specific indicator sources
- [Rest Api](../productos/rest-api.md) — programmatic access to indicator data
