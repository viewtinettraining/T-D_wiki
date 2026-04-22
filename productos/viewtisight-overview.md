---
tags: [productos, viewtisight, analytics, bi]
tipo: concepto
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ViewtiSight Overview

ViewtiSight is the analytics and business intelligence layer of the Viewtinet platform. It transforms the high-volume data ingested by [[viewtilog-overview|ViewtiLog]] into actionable, visually engaging insights for network operations and management teams.

## Purpose

ViewtiSight serves as the primary visualization and reporting interface within the Viewtinet suite. It bridges raw collected data and operational decision-making through interactive dashboards, custom metrics, automated reports, and intelligent alarms.

## Key Capabilities

- **Dashboard Composer** — Build interactive dashboards with drill-down capabilities using both real-time and historical data
- **Metrics Composer** — Define custom KPIs tailored to your organization's specific monitoring requirements
- **PDF Reporter** — Generate automated, scheduled reports in PDF format for compliance, audits, and management review
- **Control Center** — Centralized management for alarms and notifications based on thresholds or anomaly detection
- **Historical Data Access** — Leverage years of archived data for trend analysis and capacity planning

## Alarm System

ViewtiSight provides advanced alarms driven by:
- **Threshold-based rules** — Alert when a metric exceeds a defined value
- **Anomaly detection** — Alert when behavior deviates statistically from baseline patterns

Alarms can trigger notifications for rapid incident response.

## Deployment

ViewtiSight is installed automatically as part of the [[installation-bundle-steps|bundle installation]] in standalone mode. In [[standalone-vs-cluster|cluster deployments]], additional nodes are added via the [[viewtisight-installation|cluster installation procedure]].

It runs on [[ubuntu-compatibility|Ubuntu Server 20.04 or 24.04]] and is accessed via the [[gui-overview|Viewtinet GUI]] at port 8080 (HTTP) or 443 (HTTPS) in cluster mode.

## Data Flow

ViewtiSight consumes data from [[viewtilog-overview|ViewtiLog]] and [[viewtimon-overview|ViewtiMon]], presenting it through the [[viewtimanager-overview|ViewtiManager]] application selector.

For installation steps, see [[viewtisight-installation]]. See [[installation-guide-hub|Installation Guide Hub]] for related source documentation.
