---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'ViewtiSight REST API Specification PDF — Source Summary'
id: 2IP-1NB-PZM-K8H
slug: rest-api-pdf
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# ViewtiSight REST API Specification PDF — Source Summary

This page summarizes the Viewtinet ViewtiSight REST API Specification (v1.5). The REST API enables programmatic access to [ViewtiSight](../productos/viewtisight-features.md) data, dashboards, metrics, and alarms from external applications and scripts.

## API Overview

The ViewtiSight REST API is a JSON-based HTTP API exposed by the [ViewtiCore gateway](../productos/rest-api.md) container (`viewtinet-viewticore-gateway`). It allows external systems to query stored data, retrieve metric values, and interact with the Viewtinet platform programmatically.

Key use cases:
- Integrating Viewtinet data into third-party dashboards (e.g., Grafana)
- Automating report generation and data export
- Triggering or querying [alarms](../conceptos/alarms-system.md) from external tools
- Feeding data into SIEM or ITSM platforms

## Authentication

The API uses **token-based authentication**. A valid API token must be obtained from [ViewtiManager](../productos/viewtimanager-overview.md) and included in all requests as a Bearer token in the `Authorization` HTTP header:

```
Authorization: Bearer <api-token>
```

Tokens are scoped per [tenant](../configuracion/tenants.md) and respect [role-based permissions](../configuracion/roles.md). The token grants access only to data and operations permitted by the associated user role.

## Key Endpoint Categories

| Category | Description |
|----------|-------------|
| Authentication | Obtain and validate API tokens |
| Datasets (Sets) | Query time-series data from ingested datasets |
| Metrics | Retrieve computed [Metric Composer](../productos/viewtisight-features.md) values |
| Dashboards | List and export dashboard definitions |
| Alarms | Query active alarms and alarm history |
| Dimensions | Filter and group data by dimensions |

## Data Query Pattern

Queries follow the same logic as the [QueryBuilder](../productos/viewtisight-features.md) in the ViewtiSight GUI:
- Select a **set** (dataset created by a [plugin](../conceptos/data-sources-integration.md))
- Define a **time range** (start/end timestamps)
- Choose **granularity** (1m, 5m, 1h, 1d, etc.)
- Apply **dimension filters** and **aggregations**
- Specify **metrics** to retrieve

## Related Pages

- [Rest Api](../productos/rest-api.md) — detailed API reference page
- [Viewtisight Features](../productos/viewtisight-features.md) — ViewtiSight analytics and dashboard features
- [Data Sources Integration](../conceptos/data-sources-integration.md) — how data is ingested and made available
- [Alarms System](../conceptos/alarms-system.md) — alarms accessible via API
- [Tenants](../configuracion/tenants.md) — multi-tenant scoping of API access
- [Roles](../configuracion/roles.md) — role-based access control for API tokens
