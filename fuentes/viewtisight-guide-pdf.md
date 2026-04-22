---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'ViewtiSight User Guide PDF — Source Summary'
id: N6G-M50-KXW-XDY
slug: viewtisight-guide-pdf
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# ViewtiSight User Guide PDF — Source Summary

This page summarizes the ViewtiSight User Guide (v6.3), the official end-user reference for [ViewtiSight](../productos/viewtisight-overview.md) — Viewtinet's analytics and business intelligence layer. The guide covers all major features accessible through the ViewtiSight interface.

## Scope and Audience

The guide targets analysts, NOC operators, and administrators who use [ViewtiSight](../productos/viewtisight-features.md) to build dashboards, define metrics, configure alarms, and generate reports. It assumes the platform has been installed (see [Installation Bundle](../instalacion/installation-bundle.md)) and data is flowing through the [ETL pipeline](../conceptos/etl-pipeline.md).

## Key Sections Covered

### Dashboard Composer

The guide details how to create, organize, and share dashboards. Topics include:

- Creating a new dashboard and adding widgets
- Configuring widget data sources using the [QueryBuilder](../productos/viewtisight-features.md)
- Setting time ranges, granularity, and auto-refresh intervals
- Applying dimension filters and grouping
- Sharing dashboards across [user groups](../configuracion/groups.md) and [tenants](../configuracion/tenants.md)
- Drill-down navigation between summary and detail views

### Metrics Composer

Step-by-step instructions for defining custom KPIs:

- Selecting a dataset from a [VSDB plugin](../conceptos/data-sources-integration.md)
- Choosing aggregation functions and dimension grouping
- Saving and naming metrics for reuse in dashboards and [alarms](../conceptos/alarms-system.md)

### Control Center (Alarms)

The guide covers the full alarm management workflow as documented in the Alarms User Guide:

- Viewing and filtering active alarms by severity (Critical, Major, Minor, Clear)
- Acknowledging, silencing, hiding, and resetting alarms
- Adding shared comments to alarm records
- Accessing the Events Log for historical alarm data

See [Alarms System](../conceptos/alarms-system.md) for the full alarms conceptual overview.

### PDF Reporter

Instructions for scheduling and generating PDF reports:

- Selecting dashboards to include in a report
- Configuring cron-based delivery schedules
- Setting up email delivery (requires SMTP in [ViewtiManager](../productos/viewtimanager-overview.md))

### REST API Access

The guide references the [ViewtiSight REST API](../productos/rest-api.md) for users who need programmatic data access. API tokens are obtained from [ViewtiManager](../productos/viewtimanager-overview.md) and scoped to [tenant](../configuracion/tenants.md) and [role](../configuracion/roles.md) permissions.

## Authentication and Access Control

All ViewtiSight access is authenticated via [ViewtiAuth](../integraciones/viewtiauth.md). The guide covers:

- Login flow and session management
- Role-based feature visibility — some features require admin [roles](../configuracion/roles.md)
- [Multi-factor authentication](../integraciones/mfa-configuration.md) prompts if enabled
- [Active Directory](../integraciones/active-directory.md) and [LDAP](../integraciones/ldap-integration.md) SSO behavior

## Deployment Context

The guide applies to ViewtiSight running in both [standalone and cluster (HA)](../conceptos/standalone-vs-cluster.md) modes. In HA mode, users connect through the [floating VIP](../conceptos/ha-architecture.md) managed by Keepalived. The application is accessible at port 8080 (HTTP) or 443 (HTTPS).

## Related Pages

- [Viewtisight Features](../productos/viewtisight-features.md) — detailed feature reference for ViewtiSight
- [Rest Api](../productos/rest-api.md) — REST API specification and endpoint catalog
- [Alarms System](../conceptos/alarms-system.md) — alarms configuration and notification channels
- [Data Sources Integration](../conceptos/data-sources-integration.md) — data flowing into ViewtiSight
- [Viewtimanager Overview](../productos/viewtimanager-overview.md) — managing ViewtiSight from the admin GUI
