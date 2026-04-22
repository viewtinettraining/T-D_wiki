---
title: "Viewtinet Solution Description PDF — Source Summary"
description: "This page summarizes the Viewtinet Solution Description document (May 2019, v2). It provides a high-level overview of the complete Viewtinet platform, its pr..."
keywords: "fuentes, plataforma, descripcion, overview"
---

# Viewtinet Solution Description PDF — Source Summary

This page summarizes the Viewtinet Solution Description document (May 2019, v2). It provides a high-level overview of the complete [Viewtinet platform](../productos/viewtinet-platform-overview.md), its product modules, target audience, architecture, and differentiating capabilities.

## Platform Purpose

The Viewtinet platform addresses the need for unified, end-to-end network visibility across heterogeneous environments — including IT, OT, and IoT infrastructures. It consolidates monitoring, analytics, traffic management, and log analysis into a single integrated solution, eliminating the need for multiple point tools.

The platform is designed for:
- **Enterprises** requiring visibility into complex multi-vendor networks
- **Service providers** managing customer environments with multi-tenant separation
- **NOC/SOC teams** needing real-time alerting and historical trend analysis

## Product Modules Described

| Module | Role |
|--------|------|
| [ViewtiManager](../productos/viewtimanager-overview.md) | Central administration and control plane |
| [ViewtiSight](../productos/viewtisight-overview.md) | Analytics, dashboards, and BI reporting |
| [ViewtiLog](../productos/viewtilog-overview.md) | Centralized log and flow management |
| [ViewtiMon](../productos/viewtimon-overview.md) | Deep Packet Inspection traffic monitoring |
| [ViewtiQoS](../productos/viewtiqos-overview.md) | Traffic shaping and QoS enforcement |
| [VS Data Broker](../productos/vs-data-broker-overview.md) | Plugin-based ETL data integration engine |
| [ViewtiBot](../productos/viewtibot-overview.md) | Chatbot and automation interface |

## Architecture Highlights

- All modules run as Docker containers on [Ubuntu Server](../conceptos/ubuntu-compatibility.md)
- Data flows through the [ETL pipeline](../conceptos/etl-pipeline.md) into a time-series database (Viewticore)
- The [plugin system](../conceptos/plugin-architecture.md) enables integration with any vendor or protocol
- [High Availability](../conceptos/ha-architecture.md) is supported via Keepalived (VIP) and HAProxy for production deployments
- [Standalone and cluster](../conceptos/standalone-vs-cluster.md) deployment modes are both supported

## Key Differentiators

- **Single platform** — replaces multiple siloed tools with one integrated solution
- **Protocol agnostic** — SNMP, NetFlow, sFlow, Syslog, WMI, SSH, and more via [data source integration](../conceptos/data-sources-integration.md)
- **Visual ETL** — no-code pipeline building in [VS Data Broker](../productos/vs-data-broker-overview.md)
- **Multi-tenant** — [tenant isolation](../configuracion/tenants.md) for MSP and multi-department deployments
- **Appliance or software** — deployable on [Viewtinet appliances](../productos/viewtinet-appliance.md) or commodity hardware

## Deployment and Licensing

The platform is delivered as an [installation bundle](../instalacion/installation-bundle.md) applied on top of an Ubuntu Server base. Licensing is per module and per node — see [Upload License](../instalacion/upload-license.md) and [License Management](../configuracion/license-management.md). Each server requires a license key generated from the server's hardware fingerprint.

## Related Pages

- [Viewtinet Platform Overview](../productos/viewtinet-platform-overview.md) — full platform overview wiki page
- [Viewtisight Features](../productos/viewtisight-features.md) — ViewtiSight analytics features
- [Rest Api](../productos/rest-api.md) — REST API for programmatic access
- [Alarms System](../conceptos/alarms-system.md) — alerting and notification system
- [Cli Reference](../conceptos/cli-reference.md) — command-line administration
