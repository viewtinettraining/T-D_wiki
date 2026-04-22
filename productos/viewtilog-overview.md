---
title: "ViewtiLog Overview"
description: "ViewtiLog is Viewtinet's comprehensive log management and analysis solution. It centralizes log collection from diverse infrastructure sources and transforms..."
keywords: "productos, viewtilog, logs"
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

ViewtiLog is designed to integrate seamlessly with the Viewtinet platform. It feeds data into [ViewtiSight](viewtisight-overview.md) for analytics and visualization, and is managed through [ViewtiManager](viewtimanager-overview.md).

In HA deployments, ViewtiLog operates as a cluster with a floating VIP managed by Keepalived and HAProxy for load balancing and automatic failover. See [Standalone Vs Cluster](../conceptos/standalone-vs-cluster.md) for deployment modes.

## Deployment

ViewtiLog runs on [Ubuntu Server 20.04 or 24.04](../conceptos/ubuntu-compatibility.md) as containerized services. It requires the [Installation Bundle](../instalacion/installation-bundle.md) to be installed first and uses the [ViewtiManager](viewtimanager-overview.md) GUI for module installation and configuration.

For installation steps, see [Viewtilog Installation](../instalacion/viewtilog-installation.md).

## Data Sources

| Source Type | Protocol |
|---|---|
| Network devices | SNMP, NetFlow/IPFIX |
| Servers/Applications | Syslog |
| Telephony | CDR (Call Detail Records) |
| APIs | REST API polling |

See [Installation Guide Hub](../fuentes/installation-guide-hub.md) for related source documentation.
