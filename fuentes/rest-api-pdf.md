---
tags: [fuentes, api, rest, viewtisight]
tipo: fuente
fuentes: ["Viewtinet_Viewtisight_REST_API_Specification-v1.5"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ViewtiSight REST API Specification PDF — Source Summary

This page summarizes the Viewtinet ViewtiSight REST API Specification (v1.5). The REST API enables programmatic access to [[viewtisight-features|ViewtiSight]] data, dashboards, metrics, and alarms from external applications and scripts.

## API Overview

The ViewtiSight REST API is a JSON-based HTTP API exposed by the [[rest-api|ViewtiCore gateway]] container (`viewtinet-viewticore-gateway`). It allows external systems to query stored data, retrieve metric values, and interact with the Viewtinet platform programmatically.

Key use cases:
- Integrating Viewtinet data into third-party dashboards (e.g., Grafana)
- Automating report generation and data export
- Triggering or querying [[alarms-system|alarms]] from external tools
- Feeding data into SIEM or ITSM platforms

## Authentication

The API uses **token-based authentication**. A valid API token must be obtained from [[viewtimanager-overview|ViewtiManager]] and included in all requests as a Bearer token in the `Authorization` HTTP header:

```
Authorization: Bearer <api-token>
```

Tokens are scoped per [[tenants|tenant]] and respect [[roles|role-based permissions]]. The token grants access only to data and operations permitted by the associated user role.

## Key Endpoint Categories

| Category | Description |
|----------|-------------|
| Authentication | Obtain and validate API tokens |
| Datasets (Sets) | Query time-series data from ingested datasets |
| Metrics | Retrieve computed [[viewtisight-features|Metric Composer]] values |
| Dashboards | List and export dashboard definitions |
| Alarms | Query active alarms and alarm history |
| Dimensions | Filter and group data by dimensions |

## Data Query Pattern

Queries follow the same logic as the [[viewtisight-features|QueryBuilder]] in the ViewtiSight GUI:
- Select a **set** (dataset created by a [[data-sources-integration|plugin]])
- Define a **time range** (start/end timestamps)
- Choose **granularity** (1m, 5m, 1h, 1d, etc.)
- Apply **dimension filters** and **aggregations**
- Specify **metrics** to retrieve

## Related Pages

- [[rest-api]] — detailed API reference page
- [[viewtisight-features]] — ViewtiSight analytics and dashboard features
- [[data-sources-integration]] — how data is ingested and made available
- [[alarms-system]] — alarms accessible via API
- [[tenants]] — multi-tenant scoping of API access
- [[roles]] — role-based access control for API tokens
