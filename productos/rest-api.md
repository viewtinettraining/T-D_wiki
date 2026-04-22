---
tags: [productos, api, rest, viewtisight, integracion]
tipo: tecnica
fuentes: ["Viewtinet_Viewtisight_REST_API_Specification-v1.5"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# ViewtiSight REST API

The ViewtiSight REST API is a JSON-based HTTP interface that enables programmatic access to [[viewtisight-overview|ViewtiSight]] data, dashboards, metrics, and alarms. It is exposed by the `viewtinet-viewticore-gateway` container and follows standard REST conventions.

## Authentication

The API uses **Bearer token authentication**. Tokens are obtained from [[viewtimanager-overview|ViewtiManager]] and must be included in every request:

```
Authorization: Bearer <api-token>
```

- Tokens are scoped per [[tenants|tenant]] and enforce [[roles|role-based permissions]]
- A token grants access only to the data and operations permitted by the associated user role
- Tokens are revocable from ViewtiManager's admin panel

## Base URL

```
https://<VIP-or-host>:<port>/api/v1/
```

In [[ha-architecture|HA cluster deployments]], the base URL resolves to the floating Virtual IP managed by Keepalived. In standalone mode, it resolves directly to the server IP.

## Key Endpoint Categories

| Category | Path Prefix | Description |
|----------|-------------|-------------|
| Authentication | `/auth/` | Obtain and validate API tokens |
| Datasets (Sets) | `/sets/` | Query time-series data from ingested datasets |
| Metrics | `/metrics/` | Retrieve computed [[viewtisight-features|Metrics Composer]] values |
| Dashboards | `/dashboards/` | List and export dashboard definitions |
| Alarms | `/alarms/` | Query active alarms and alarm history |
| Dimensions | `/dimensions/` | Filter and group data by dimension values |
| Plugins | `/plugins/` | List active [[plugin-architecture|plugins]] and their datasets |

## Data Query Pattern

All dataset queries follow a consistent structure matching the [[viewtisight-features|QueryBuilder]] logic:

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

- Integrating Viewtinet data into third-party dashboards (e.g., Grafana, Kibana)
- Automating report generation and data export to data lakes
- Triggering or querying [[alarms-system|alarms]] from ITSM or SIEM tools
- Building custom portals that surface [[data-sources-integration|plugin]] data to end users
- Feeding network telemetry into ML pipelines

## Related Pages

- [[viewtisight-features]] — GUI features powered by the same data engine
- [[alarms-system]] — alarm endpoints and notification channels
- [[data-sources-integration]] — how data flows into queryable datasets
- [[tenants]] — multi-tenant access scoping
- [[roles]] — role-based API token permissions
- [[ha-architecture]] — cluster endpoint resolution via VIP
