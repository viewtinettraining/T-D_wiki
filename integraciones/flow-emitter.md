---
tags: [integraciones, vsdb, extractor, dpi]
tipo: tecnica
fuentes: ["flow-emitter"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Flow Emitter

The Flow Emitter Connector is a specialized extractor within the [[vs-data-broker-overview|VS Data Broker]] that exposes data processed by the Viewtimon DPI (Deep Packet Inspection) engine. Unlike connectors such as [[snmp-extractor]], [[csv-extractor]], or [[ssh-extractor]] — which pull data from external devices — the Flow Emitter is strictly internal to the Viewtinet platform.

## Purpose

The Flow Emitter reads classified, DPI-enriched flow data from the [[viewtimon-overview|Viewtimon]] engine and exports it as plain text records. These records carry detailed per-flow metrics covering network identity, TCP/UDP session quality, application classification, and performance indicators.

This connector is the primary bridge between Viewtimon's real-time traffic analysis capabilities and the [[etl-pipeline]] for storage, aggregation, and reporting.

## Key Characteristics

- **Internal use only**: tied to the Viewtimon DPI engine. No external IP, port, or OID configuration is required.
- Exports data in plain text format, ready for the Transform stage.
- Fixed field set determined by DPI engine capabilities — not user-configurable.
- Ideal for deep traffic visibility use cases: application performance monitoring, Quality of Experience (QoE) analysis, and advanced troubleshooting.

## Available Fields

The Flow Emitter outputs a large set of predefined fields. Representative examples:

**Basic Network Identifiers**
- `net_src_ip`, `net_dst_ip` — source and destination IP addresses
- `net_src_port`, `net_dst_port` — source and destination ports
- `ip_protocol` — protocol number (TCP, UDP, ICMP)

**ICMP Metrics**
- `icmp_rtt` — round-trip time for ICMP probes
- `icmp_packet_loss` — percentage of ICMP packet loss

**TCP Session Metrics**
- `tcp_rtt_client`, `tcp_rtt_server` — per-direction round-trip times
- `tcp_time_to_first_byte` — elapsed time to first byte received
- `tcp_retransmissions_client`, `tcp_retransmissions_server`
- `tcp_window_size_client`, `tcp_window_size_server`

**Application-Level Metrics**
- `app_name` — application detected by DPI (e.g., HTTP, Skype, YouTube)
- `dpi_name` — DPI classifier name
- `policy_id`, `policy_name` — associated policy rules

**Performance Indicators**
- `volume_uplink`, `volume_downlink` — total traffic volume per flow
- `app_jitter`, `app_packet_loss` — application-level quality metrics
- `dns_query_count`, `dns_response_count` — DNS activity counters
- `session_duration` — lifetime of the detected flow
- `vlan_id` — VLAN tag associated with the flow

## Usage in the ETL Pipeline

Data from the Flow Emitter typically passes through the Transform stage (Grid Handlers) before reaching a [[data-producers|Producer]]. Common transformations include normalization, field enrichment, or field mapping.

Because the field set is fixed, no external parameters are configured for this connector. It can be used as the Extract stage of a [[customized-plugin]] targeting Viewtimon data. See [[plugin-architecture]] for how plugins are assembled and [[column-constant-adder]] for an example Transform operation.
