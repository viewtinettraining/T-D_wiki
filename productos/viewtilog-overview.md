---
tags: [productos, viewtilog, logs]
tipo: concepto
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ViewtiLog Overview

ViewtiLog is Viewtinet's comprehensive log management and analysis solution. It centralizes log collection from diverse infrastructure sources and transforms raw log data into actionable operational and security intelligence.

## Purpose

ViewtiLog addresses the challenge of managing log data at scale across heterogeneous environments. Rather than relying on disparate per-device logging, it provides a single platform for ingestion, normalization, correlation, and visualization of logs from any source.

## Key Capabilities

- **Centralized Log Collection** — Collects logs from servers, network devices, applications, and other sources including syslog, NetFlow/IPFIX, SNMP, and CDRs
- **Real-Time Monitoring** — Processes and displays log events as they arrive, enabling rapid detection of incidents
- **Advanced Analytics and Pattern Detection** — Identifies anomalies, trends, and patterns across large volumes of log data
- **Customizable Dashboards** — Provides flexible dashboards tailored to different operational needs
- **Automated Alerts** — Triggers notifications based on configurable conditions or anomaly detection
- **Detailed Reports** — Generates structured reports for compliance, audits, and operational reviews

## Integration

ViewtiLog is designed to integrate seamlessly with the Viewtinet platform. It feeds data into [[viewtisight-overview|ViewtiSight]] for analytics and visualization, and is managed through [[viewtimanager-overview|ViewtiManager]].

In HA deployments, ViewtiLog operates as a cluster with a floating VIP managed by Keepalived and HAProxy for load balancing and automatic failover. See [[standalone-vs-cluster]] for deployment modes.

## Deployment

ViewtiLog runs on [[ubuntu-compatibility|Ubuntu Server 20.04 or 24.04]] as containerized services. It requires the [[installation-bundle]] to be installed first and uses the [[viewtimanager-overview|ViewtiManager]] GUI for module installation and configuration.

For installation steps, see [[viewtilog-installation]].

## Data Sources

| Source Type | Protocol |
|---|---|
| Network devices | SNMP, NetFlow/IPFIX |
| Servers/Applications | Syslog |
| Telephony | CDR (Call Detail Records) |
| APIs | REST API polling |

See [[installation-guide-hub|Installation Guide Hub]] for related source documentation.
