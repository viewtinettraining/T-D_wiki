---
tags: [fuentes, plataforma, descripcion, overview]
tipo: fuente
fuentes: ["Viewtinet Solution Description 052019v2"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Viewtinet Solution Description PDF — Source Summary

This page summarizes the Viewtinet Solution Description document (May 2019, v2). It provides a high-level overview of the complete [[viewtinet-platform-overview|Viewtinet platform]], its product modules, target audience, architecture, and differentiating capabilities.

## Platform Purpose

The Viewtinet platform addresses the need for unified, end-to-end network visibility across heterogeneous environments — including IT, OT, and IoT infrastructures. It consolidates monitoring, analytics, traffic management, and log analysis into a single integrated solution, eliminating the need for multiple point tools.

The platform is designed for:
- **Enterprises** requiring visibility into complex multi-vendor networks
- **Service providers** managing customer environments with multi-tenant separation
- **NOC/SOC teams** needing real-time alerting and historical trend analysis

## Product Modules Described

| Module | Role |
|--------|------|
| [[viewtimanager-overview|ViewtiManager]] | Central administration and control plane |
| [[viewtisight-overview|ViewtiSight]] | Analytics, dashboards, and BI reporting |
| [[viewtilog-overview|ViewtiLog]] | Centralized log and flow management |
| [[viewtimon-overview|ViewtiMon]] | Deep Packet Inspection traffic monitoring |
| [[viewtiqos-overview|ViewtiQoS]] | Traffic shaping and QoS enforcement |
| [[vs-data-broker-overview|VS Data Broker]] | Plugin-based ETL data integration engine |
| [[viewtibot-overview|ViewtiBot]] | Chatbot and automation interface |

## Architecture Highlights

- All modules run as Docker containers on [[ubuntu-compatibility|Ubuntu Server]]
- Data flows through the [[etl-pipeline|ETL pipeline]] into a time-series database (Viewticore)
- The [[plugin-architecture|plugin system]] enables integration with any vendor or protocol
- [[ha-architecture|High Availability]] is supported via Keepalived (VIP) and HAProxy for production deployments
- [[standalone-vs-cluster|Standalone and cluster]] deployment modes are both supported

## Key Differentiators

- **Single platform** — replaces multiple siloed tools with one integrated solution
- **Protocol agnostic** — SNMP, NetFlow, sFlow, Syslog, WMI, SSH, and more via [[data-sources-integration|data source integration]]
- **Visual ETL** — no-code pipeline building in [[vs-data-broker-overview|VS Data Broker]]
- **Multi-tenant** — [[tenants|tenant isolation]] for MSP and multi-department deployments
- **Appliance or software** — deployable on [[viewtinet-appliance|Viewtinet appliances]] or commodity hardware

## Deployment and Licensing

The platform is delivered as an [[installation-bundle|installation bundle]] applied on top of an Ubuntu Server base. Licensing is per module and per node — see [[upload-license]] and [[license-management]]. Each server requires a license key generated from the server's hardware fingerprint.

## Related Pages

- [[viewtinet-platform-overview]] — full platform overview wiki page
- [[viewtisight-features]] — ViewtiSight analytics features
- [[rest-api]] — REST API for programmatic access
- [[alarms-system]] — alerting and notification system
- [[cli-reference]] — command-line administration
