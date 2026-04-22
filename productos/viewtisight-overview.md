---
title: "ViewtiSight Overview"
description: "ViewtiSight is the analytics and business intelligence layer of the Viewtinet platform. It transforms the high-volume data ingested by ViewtiLog into actiona..."
keywords: "productos, viewtisight, analytics, bi"
---

# ViewtiSight Overview

ViewtiSight is the analytics and business intelligence layer of the Viewtinet platform. It transforms the high-volume data ingested by [ViewtiLog](viewtilog-overview.md) into actionable, visually engaging insights for network operations and management teams.

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

ViewtiSight is installed automatically as part of the [bundle installation](../instalacion/installation-bundle-steps.md) in standalone mode. In [cluster deployments](../conceptos/standalone-vs-cluster.md), additional nodes are added via the [cluster installation procedure](../instalacion/viewtisight-installation.md).

It runs on [Ubuntu Server 20.04 or 24.04](../conceptos/ubuntu-compatibility.md) and is accessed via the [Viewtinet GUI](../configuracion/gui-overview.md) at port 8080 (HTTP) or 443 (HTTPS) in cluster mode.

## Data Flow

ViewtiSight consumes data from [ViewtiLog](viewtilog-overview.md) and [ViewtiMon](viewtimon-overview.md), presenting it through the [ViewtiManager](viewtimanager-overview.md) application selector.

For installation steps, see [Viewtisight Installation](../instalacion/viewtisight-installation.md). See [Installation Guide Hub](../fuentes/installation-guide-hub.md) for related source documentation.
