---
title: "Viewtinet Platform Overview"
description: "Viewtinet is an integrated network monitoring, analytics, and management platform designed for enterprises, service providers, and operators that need unifie..."
keywords: "productos, plataforma, arquitectura, overview"
---

# Viewtinet Platform Overview

Viewtinet is an integrated network monitoring, analytics, and management platform designed for enterprises, service providers, and operators that need unified visibility across their IT, OT, and IoT environments. It delivers end-to-end intelligence — from raw traffic capture to business intelligence dashboards — through a modular, containerized architecture.

## Product Suite

The Viewtinet platform is composed of several specialized modules, all managed through a single control plane:

| Module | Role |
|--------|------|
| [ViewtiManager](viewtimanager-overview.md) | Central administration GUI — user management, configuration, licensing |
| [ViewtiSight](viewtisight-overview.md) | Analytics and BI layer — dashboards, metrics, reports, alarms |
| [ViewtiLog](viewtilog-overview.md) | Log management and analysis — syslog, NetFlow, CDR, SNMP |
| [ViewtiMon](viewtimon-overview.md) | Deep packet inspection and real-time traffic monitoring |
| [ViewtiQoS](viewtiqos-overview.md) | Traffic shaping and QoS policy enforcement |
| [VS Data Broker](vs-data-broker-overview.md) | Visual ETL engine — plugin-based data ingestion pipeline |
| [ViewtiBot](viewtibot-overview.md) | Automation and chatbot integration module |
| [ViewtiAuth](../integraciones/viewtiauth.md) | Authentication service with MFA, LDAP, and AD support |

## Target Audience

- **Network Operations Centers (NOC)** — real-time monitoring, incident detection, and capacity planning
- **Enterprise IT teams** — centralized log management, compliance reporting, and configuration automation
- **Service providers** — multi-tenant environments with per-customer dashboards and SLA tracking
- **Security teams** — anomaly detection, syslog correlation, and flow analysis

## Architecture

The Viewtinet platform runs as Docker containers on [Ubuntu Server 20.04 or 24.04](../conceptos/ubuntu-compatibility.md). All components are installed from the [installation bundle](../instalacion/installation-bundle.md) and managed by [ViewtiManager](viewtimanager-overview.md).

Core infrastructure components:
- **Viewticore** — the central data engine and time-series database (TimescaleDB-backed)
- **ViewtiAuth** — handles authentication across all modules; supports [Active Directory](../integraciones/active-directory.md), [LDAP](../integraciones/ldap-integration.md), and [MFA](../integraciones/mfa-configuration.md)
- **[ETL Pipeline](../conceptos/etl-pipeline.md)** — driven by the [VS Data Broker](vs-data-broker-overview.md) plugin system
- **[High Availability](../conceptos/ha-architecture.md)** — active-passive cluster using Keepalived (VIP) and HAProxy (load balancing) for supported modules

## Deployment Modes

Two deployment modes are available — see [Standalone Vs Cluster](../conceptos/standalone-vs-cluster.md):

- **Standalone** — single server; suitable for dev/test or smaller deployments
- **Cluster (HA)** — two or more nodes with automatic failover; recommended for production

ViewtiMon and ViewtiQoS support standalone mode only.

## Data Flow Summary

1. Data is ingested through [protocol extractors](../conceptos/data-sources-integration.md) (SNMP, NetFlow, Syslog, etc.) configured in [VS Data Broker](vs-data-broker-overview.md) plugins
2. The [ETL pipeline](../conceptos/etl-pipeline.md) transforms and loads data into Viewticore's time-series database
3. [ViewtiSight](viewtisight-overview.md) presents the data through dashboards, metrics, and the [REST API](rest-api.md)
4. [Alarms](../conceptos/alarms-system.md) notify operations teams via email, Telegram, Teams, or WhatsApp

## Use Cases

- End-to-end network visibility from L2 to L7
- Application performance monitoring and SLA validation
- NetFlow/IPFIX traffic accounting and reporting
- Multi-vendor device monitoring via SNMP and SSH
- Centralized syslog collection and security correlation
- Configuration management and [device autodiscovery](../configuracion/autodiscovery.md)
