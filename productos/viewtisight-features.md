---
title: "ViewtiSight Features"
description: "ViewtiSight is the analytics and business intelligence layer of the Viewtinet platform. It provides a complete suite of tools for data exploration, dashboard..."
keywords: "productos, viewtisight, analytics, dashboards, bi"
---

# ViewtiSight Features

[ViewtiSight](viewtisight-overview.md) is the analytics and business intelligence layer of the Viewtinet platform. It provides a complete suite of tools for data exploration, dashboard building, metric definition, automated reporting, and alarm management — all accessible through the [Viewtinet GUI](../configuracion/gui-overview.md).

## Dashboard Composer

The Dashboard Composer is the primary visualization interface in ViewtiSight. Administrators and analysts can build fully interactive dashboards from any data ingested by the [ETL pipeline](../conceptos/etl-pipeline.md). Key capabilities include:

- **Widget library** — charts, tables, gauges, maps, topologies, and text panels
- **Drill-down navigation** — click through from aggregate views to per-device or per-flow detail
- **Time range selector** — fixed or rolling time windows (last 15 minutes to multiple years)
- **Multi-tenant scoping** — dashboards are restricted by [tenant](../configuracion/tenants.md) and [role](../configuracion/roles.md)
- **Real-time and historical views** — mix live data with archived time-series from TimescaleDB

Dashboards are organized in folders and can be shared across [user groups](../configuracion/groups.md) or kept private per user.

## Metrics Composer

The Metrics Composer allows defining custom KPIs on top of ingested datasets. Metrics are computed from the data produced by [VS Data Broker](vs-data-broker-overview.md) plugins and can reference:

- Aggregation functions (sum, average, max, min, percentile)
- Dimension filters and group-by clauses
- Time-window calculations

Metrics feed the [alarms system](../conceptos/alarms-system.md) (scheduled alarms evaluate Metrics Composer outputs) and appear as selectable data series in Dashboard widgets.

## QueryBuilder

The QueryBuilder is the data exploration engine behind every dashboard widget. Users select:

1. A **set** (dataset) produced by a [plugin](../conceptos/data-sources-integration.md)
2. A **time range** and **granularity** (1m, 5m, 1h, 1d, etc.)
3. **Dimension filters** — device, interface, application, location, etc.
4. **Aggregation** — how rows are grouped before display

The same query logic is exposed in the [REST API](rest-api.md), enabling programmatic data access.

## PDF Reporter

ViewtiSight generates scheduled PDF reports for compliance, management review, and SLA documentation. Reports are built from saved dashboards and delivered by email or stored on the server. Scheduling is configured with cron-like intervals.

## Control Center (Alarms)

The Control Center provides alarm management within ViewtiSight. It displays active alarms with severity levels (Critical, Major, Minor, Clear) and supports acknowledgment, silencing, hiding, and commenting. See [Alarms System](../conceptos/alarms-system.md) for full configuration and notification details.

## Data Access and Integration

- ViewtiSight consumes data from [ViewtiLog](viewtilog-overview.md) and [ViewtiMon](viewtimon-overview.md) via Viewticore
- External tools access data through the [ViewtiSight REST API](rest-api.md)
- User access is controlled by [ViewtiAuth](../integraciones/viewtiauth.md) with optional [MFA](../integraciones/mfa-configuration.md) and [LDAP](../integraciones/ldap-integration.md) integration
- In HA deployments, ViewtiSight operates behind the [HAProxy/Keepalived VIP](../conceptos/ha-architecture.md)
