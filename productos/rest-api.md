---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'ViewtiSight REST API'
id: JC7-0V8-SR5-LQB
slug: rest-api
isVisible: true
isSearchable: true
lastUpdated: '2026-04-22 08:56:45'
---
# ViewtiSight REST API

The ViewtiSight REST API is a JSON-based HTTP interface that enables programmatic access to [ViewtiSight](viewtisight-overview.md) data, dashboards, metrics, and alarms. It is exposed by the `viewtinet-viewticore-gateway` container and follows standard REST conventions.

## Authentication

The API uses **Bearer token authentication**. Tokens are obtained from [ViewtiManager](viewtimanager-overview.md) and must be included in every request:

```
Authorization: Bearer <api-token>
```

-   Tokens are scoped per [tenant](../configuracion/tenants.md) and enforce [role-based permissions](../configuracion/roles.md)
-   A token grants access only to the data and operations permitted by the associated user role
-   Tokens are revocable from ViewtiManager's admin panel

## Base URL

```
https://<VIP-or-host>:<port>/api/v1/
```

In [HA cluster deployments](../conceptos/ha-architecture.md), the base URL resolves to the floating Virtual IP managed by Keepalived. In standalone mode, it resolves directly to the server IP.

## Key Endpoint Categories

<table><tbody><tr><th><p>Category</p></th><th><p>Path Prefix</p></th><th><p>Description</p></th></tr><tr><td><p>Authentication</p></td><td><p><code>/auth/</code></p></td><td><p>Obtain and validate API tokens</p></td></tr><tr><td><p>Datasets (Sets)</p></td><td><p><code>/sets/</code></p></td><td><p>Query time-series data from ingested datasets</p></td></tr><tr><td><p>Metrics</p></td><td><p><code>/metrics/</code></p></td><td><p>Retrieve computed <a href="viewtisight-features.md" target="_blank">Metrics Composer</a> values</p></td></tr><tr><td><p>Dashboards</p></td><td><p><code>/dashboards/</code></p></td><td><p>List and export dashboard definitions</p></td></tr><tr><td><p>Alarms</p></td><td><p><code>/alarms/</code></p></td><td><p>Query active alarms and alarm history</p></td></tr><tr><td><p>Dimensions</p></td><td><p><code>/dimensions/</code></p></td><td><p>Filter and group data by dimension values</p></td></tr><tr><td><p>Plugins</p></td><td><p><code>/plugins/</code></p></td><td><p>List active <a href="../conceptos/plugin-architecture.md" target="_blank">plugins</a> and their datasets</p></td></tr></tbody></table>

## Data Query Pattern

All dataset queries follow a consistent structure matching the [QueryBuilder](viewtisight-features.md) logic:

```json
{
  "set": "dataset-name",
  "from": "2026-04-22T00:00:00Z",
  "to":   "2026-04-22T01:00:00Z",
  "granularity": "5m",
  "filters": [
    { "dimension": "device", "operator": "eq", "value": "router-01" }
  ],
  "metrics": ["bytes_in", "bytes_out", "packets"]
}
```

Granularity options: `1m`, `5m`, `15m`, `1h`, `1d`.

## Response Format

All responses return JSON with HTTP 200 on success. Errors return standard HTTP codes (400, 401, 403, 404, 500) with a JSON body containing a `message` field.

```json
{
  "status": "ok",
  "data": [ ... ],
  "meta": { "total": 120, "granularity": "5m" }
}
```

## Common Use Cases

-   Integrating Viewtinet data into third-party dashboards (e.g., Grafana, Kibana)
-   Automating report generation and data export to data lakes
-   Triggering or querying [alarms](../conceptos/alarms-system.md) from ITSM or SIEM tools
-   Building custom portals that surface [plugin](../conceptos/data-sources-integration.md) data to end users
-   Feeding network telemetry into ML pipelines

## Related Pages

-   [Viewtisight Features](viewtisight-features.md) — GUI features powered by the same data engine
-   [Alarms System](../conceptos/alarms-system.md) — alarm endpoints and notification channels
-   [Data Sources Integration](../conceptos/data-sources-integration.md) — how data flows into queryable datasets
-   [Tenants](../configuracion/tenants.md) — multi-tenant access scoping
-   [Roles](../configuracion/roles.md) — role-based API token permissions
-   [Ha Architecture](../conceptos/ha-architecture.md) — cluster endpoint resolution via VIP

<br />