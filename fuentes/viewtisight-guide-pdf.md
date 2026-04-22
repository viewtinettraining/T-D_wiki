---
tags: [fuentes, viewtisight, guia, usuario, analytics]
tipo: fuente
fuentes: ["viewtisight-user-guide_en_v6.3"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# ViewtiSight User Guide PDF — Source Summary

This page summarizes the ViewtiSight User Guide (v6.3), the official end-user reference for [[viewtisight-overview|ViewtiSight]] — Viewtinet's analytics and business intelligence layer. The guide covers all major features accessible through the ViewtiSight interface.

## Scope and Audience

The guide targets analysts, NOC operators, and administrators who use [[viewtisight-features|ViewtiSight]] to build dashboards, define metrics, configure alarms, and generate reports. It assumes the platform has been installed (see [[installation-bundle]]) and data is flowing through the [[etl-pipeline|ETL pipeline]].

## Key Sections Covered

### Dashboard Composer

The guide details how to create, organize, and share dashboards. Topics include:

- Creating a new dashboard and adding widgets
- Configuring widget data sources using the [[viewtisight-features|QueryBuilder]]
- Setting time ranges, granularity, and auto-refresh intervals
- Applying dimension filters and grouping
- Sharing dashboards across [[groups|user groups]] and [[tenants|tenants]]
- Drill-down navigation between summary and detail views

### Metrics Composer

Step-by-step instructions for defining custom KPIs:

- Selecting a dataset from a [[data-sources-integration|VSDB plugin]]
- Choosing aggregation functions and dimension grouping
- Saving and naming metrics for reuse in dashboards and [[alarms-system|alarms]]

### Control Center (Alarms)

The guide covers the full alarm management workflow as documented in the Alarms User Guide:

- Viewing and filtering active alarms by severity (Critical, Major, Minor, Clear)
- Acknowledging, silencing, hiding, and resetting alarms
- Adding shared comments to alarm records
- Accessing the Events Log for historical alarm data

See [[alarms-system]] for the full alarms conceptual overview.

### PDF Reporter

Instructions for scheduling and generating PDF reports:

- Selecting dashboards to include in a report
- Configuring cron-based delivery schedules
- Setting up email delivery (requires SMTP in [[viewtimanager-overview|ViewtiManager]])

### REST API Access

The guide references the [[rest-api|ViewtiSight REST API]] for users who need programmatic data access. API tokens are obtained from [[viewtimanager-overview|ViewtiManager]] and scoped to [[tenants|tenant]] and [[roles|role]] permissions.

## Authentication and Access Control

All ViewtiSight access is authenticated via [[viewtiauth|ViewtiAuth]]. The guide covers:

- Login flow and session management
- Role-based feature visibility — some features require admin [[roles|roles]]
- [[mfa-configuration|Multi-factor authentication]] prompts if enabled
- [[active-directory|Active Directory]] and [[ldap-integration|LDAP]] SSO behavior

## Deployment Context

The guide applies to ViewtiSight running in both [[standalone-vs-cluster|standalone and cluster (HA)]] modes. In HA mode, users connect through the [[ha-architecture|floating VIP]] managed by Keepalived. The application is accessible at port 8080 (HTTP) or 443 (HTTPS).

## Related Pages

- [[viewtisight-features]] — detailed feature reference for ViewtiSight
- [[rest-api]] — REST API specification and endpoint catalog
- [[alarms-system]] — alarms configuration and notification channels
- [[data-sources-integration]] — data flowing into ViewtiSight
- [[viewtimanager-overview]] — managing ViewtiSight from the admin GUI
