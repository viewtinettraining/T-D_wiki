---
tags: [productos, viewtisight, analytics, dashboards, bi]
tipo: tecnica
fuentes: ["viewtisight-user-guide_en_v6.3", "Viewtinet_Viewtisight_REST_API_Specification-v1.5"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# ViewtiSight Features

[[viewtisight-overview|ViewtiSight]] is the analytics and business intelligence layer of the Viewtinet platform. It provides a complete suite of tools for data exploration, dashboard building, metric definition, automated reporting, and alarm management — all accessible through the [[gui-overview|Viewtinet GUI]].

## Dashboard Composer

The Dashboard Composer is the primary visualization interface in ViewtiSight. Administrators and analysts can build fully interactive dashboards from any data ingested by the [[etl-pipeline|ETL pipeline]]. Key capabilities include:

- **Widget library** — charts, tables, gauges, maps, topologies, and text panels
- **Drill-down navigation** — click through from aggregate views to per-device or per-flow detail
- **Time range selector** — fixed or rolling time windows (last 15 minutes to multiple years)
- **Multi-tenant scoping** — dashboards are restricted by [[tenants|tenant]] and [[roles|role]]
- **Real-time and historical views** — mix live data with archived time-series from TimescaleDB

Dashboards are organized in folders and can be shared across [[groups|user groups]] or kept private per user.

## Metrics Composer

The Metrics Composer allows defining custom KPIs on top of ingested datasets. Metrics are computed from the data produced by [[vs-data-broker-overview|VS Data Broker]] plugins and can reference:

- Aggregation functions (sum, average, max, min, percentile)
- Dimension filters and group-by clauses
- Time-window calculations

Metrics feed the [[alarms-system|alarms system]] (scheduled alarms evaluate Metrics Composer outputs) and appear as selectable data series in Dashboard widgets.

## QueryBuilder

The QueryBuilder is the data exploration engine behind every dashboard widget. Users select:

1. A **set** (dataset) produced by a [[data-sources-integration|plugin]]
2. A **time range** and **granularity** (1m, 5m, 1h, 1d, etc.)
3. **Dimension filters** — device, interface, application, location, etc.
4. **Aggregation** — how rows are grouped before display

The same query logic is exposed in the [[rest-api|REST API]], enabling programmatic data access.

## PDF Reporter

ViewtiSight generates scheduled PDF reports for compliance, management review, and SLA documentation. Reports are built from saved dashboards and delivered by email or stored on the server. Scheduling is configured with cron-like intervals.

## Control Center (Alarms)

The Control Center provides alarm management within ViewtiSight. It displays active alarms with severity levels (Critical, Major, Minor, Clear) and supports acknowledgment, silencing, hiding, and commenting. See [[alarms-system]] for full configuration and notification details.

## Data Access and Integration

- ViewtiSight consumes data from [[viewtilog-overview|ViewtiLog]] and [[viewtimon-overview|ViewtiMon]] via Viewticore
- External tools access data through the [[rest-api|ViewtiSight REST API]]
- User access is controlled by [[viewtiauth|ViewtiAuth]] with optional [[mfa-configuration|MFA]] and [[ldap-integration|LDAP]] integration
- In HA deployments, ViewtiSight operates behind the [[ha-architecture|HAProxy/Keepalived VIP]]
