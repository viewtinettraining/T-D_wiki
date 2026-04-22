---
tags: [productos, plataforma, arquitectura, overview]
tipo: concepto
fuentes: ["Viewtinet Solution Description 052019v2", "viewtimanager-user-guide_en_v6.3"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Viewtinet Platform Overview

Viewtinet is an integrated network monitoring, analytics, and management platform designed for enterprises, service providers, and operators that need unified visibility across their IT, OT, and IoT environments. It delivers end-to-end intelligence — from raw traffic capture to business intelligence dashboards — through a modular, containerized architecture.

## Product Suite

The Viewtinet platform is composed of several specialized modules, all managed through a single control plane:

| Module | Role |
|--------|------|
| [[viewtimanager-overview|ViewtiManager]] | Central administration GUI — user management, configuration, licensing |
| [[viewtisight-overview|ViewtiSight]] | Analytics and BI layer — dashboards, metrics, reports, alarms |
| [[viewtilog-overview|ViewtiLog]] | Log management and analysis — syslog, NetFlow, CDR, SNMP |
| [[viewtimon-overview|ViewtiMon]] | Deep packet inspection and real-time traffic monitoring |
| [[viewtiqos-overview|ViewtiQoS]] | Traffic shaping and QoS policy enforcement |
| [[vs-data-broker-overview|VS Data Broker]] | Visual ETL engine — plugin-based data ingestion pipeline |
| [[viewtibot-overview|ViewtiBot]] | Automation and chatbot integration module |
| [[viewtiauth|ViewtiAuth]] | Authentication service with MFA, LDAP, and AD support |

## Target Audience

- **Network Operations Centers (NOC)** — real-time monitoring, incident detection, and capacity planning
- **Enterprise IT teams** — centralized log management, compliance reporting, and configuration automation
- **Service providers** — multi-tenant environments with per-customer dashboards and SLA tracking
- **Security teams** — anomaly detection, syslog correlation, and flow analysis

## Architecture

The Viewtinet platform runs as Docker containers on [[ubuntu-compatibility|Ubuntu Server 20.04 or 24.04]]. All components are installed from the [[installation-bundle|installation bundle]] and managed by [[viewtimanager-overview|ViewtiManager]].

Core infrastructure components:
- **Viewticore** — the central data engine and time-series database (TimescaleDB-backed)
- **ViewtiAuth** — handles authentication across all modules; supports [[active-directory|Active Directory]], [[ldap-integration|LDAP]], and [[mfa-configuration|MFA]]
- **[[etl-pipeline|ETL Pipeline]]** — driven by the [[vs-data-broker-overview|VS Data Broker]] plugin system
- **[[ha-architecture|High Availability]]** — active-passive cluster using Keepalived (VIP) and HAProxy (load balancing) for supported modules

## Deployment Modes

Two deployment modes are available — see [[standalone-vs-cluster]]:

- **Standalone** — single server; suitable for dev/test or smaller deployments
- **Cluster (HA)** — two or more nodes with automatic failover; recommended for production

ViewtiMon and ViewtiQoS support standalone mode only.

## Data Flow Summary

1. Data is ingested through [[data-sources-integration|protocol extractors]] (SNMP, NetFlow, Syslog, etc.) configured in [[vs-data-broker-overview|VS Data Broker]] plugins
2. The [[etl-pipeline|ETL pipeline]] transforms and loads data into Viewticore's time-series database
3. [[viewtisight-overview|ViewtiSight]] presents the data through dashboards, metrics, and the [[rest-api|REST API]]
4. [[alarms-system|Alarms]] notify operations teams via email, Telegram, Teams, or WhatsApp

## Use Cases

- End-to-end network visibility from L2 to L7
- Application performance monitoring and SLA validation
- NetFlow/IPFIX traffic accounting and reporting
- Multi-vendor device monitoring via SNMP and SSH
- Centralized syslog collection and security correlation
- Configuration management and [[autodiscovery|device autodiscovery]]
