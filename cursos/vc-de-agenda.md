---
title: "VC-DE Detailed Agenda"
description: "This page documents the full agenda of the vc-de (Viewtinet Certified Data Engineer) course, including all topics, the Viewtimanager coverage section, and th..."
keywords: "cursos, vc-de, viewtilog"
---

# VC-DE Detailed Agenda

This page documents the full agenda of the [Vc De](../formacion/vc-de.md) (Viewtinet Certified Data Engineer) course, including all topics, the Viewtimanager coverage section, and the Viewtilog deep dive.

## Prerequisites Reminder

**[Vc Oa](../formacion/vc-oa.md) certification is strictly required** before enrolling in VC-DE. Participants without VCOA will not be admitted. This ensures all engineers arrive with proficiency in [Viewtisight Overview](../productos/viewtisight-overview.md), the Metrics Composer, and the [Alarms System](../conceptos/alarms-system.md).

---

## Agenda Topics

### 1. Welcome and Course Introduction

- Course objectives and assessment criteria (70% minimum on examination presentation)
- Overview of the Viewtinet certification path — see [Certification Paths](../formacion/certification-paths.md)
- Logistics and lab environment access

### 2. Viewtinet Products

- High-level review of the full suite: [Viewtisight Overview](../productos/viewtisight-overview.md), [Viewtilog Overview](../productos/viewtilog-overview.md), [Viewtimon Overview](../productos/viewtimon-overview.md), [Viewtiqos Overview](../productos/viewtiqos-overview.md)
- Relationship between components and the role of [Viewtimanager Overview](../productos/viewtimanager-overview.md)

### 3. Architecture and Software Structure

- Logical architecture: Control Plane vs. Data Plane
- Physical deployment options: StandAlone, Cluster, MSP — see [Standalone Vs Cluster](../conceptos/standalone-vs-cluster.md) and [Ha Architecture](../conceptos/ha-architecture.md)
- Software bundle structure and component interaction

### 4. Viewtinet Hardware Portfolio

- Appliance models, technical specifications, and best-fit scenarios
- Hardware selection based on traffic volume, user base, and data retention requirements

### 5. Bundle Installation (Practical Session)

- Step-by-step [Installation Bundle](../instalacion/installation-bundle.md) process
- OS prerequisites — see [Os Setup](../instalacion/os-setup.md) and [Ubuntu Compatibility](../conceptos/ubuntu-compatibility.md)
- [Viewtilog Installation](../instalacion/viewtilog-installation.md) procedures and initial validation

### 6. Viewtiauth

- Authentication architecture overview
- Authentication types: local, [Ldap Integration](../integraciones/ldap-integration.md), [Active Directory](../integraciones/active-directory.md)
- Token and session management

### 7. Viewtimanager — Deep Coverage

The Viewtimanager section is one of the most extensive in VC-DE:

- GUI & Components overview — see [Viewtimanager Overview](../productos/viewtimanager-overview.md) and [Gui Overview](../configuracion/gui-overview.md)
- Self-Monitoring: platform health visibility
- Integration with External Services: SMTP configuration, [Ldap Integration](../integraciones/ldap-integration.md)
- **User, Group, and Role Management** — see [Users](../configuracion/users.md) and [Roles](../configuracion/roles.md)
- **Tenants** — multi-tenant configuration for MSP deployments — see [Tenants](../configuracion/tenants.md)
- [Inventory Management](../configuracion/inventory-management.md) — device registration and asset tracking
- [Autodiscovery](../configuracion/autodiscovery.md) — automatic device detection and onboarding

### 8. Viewtilog — Deep Dive

This is the central technical section of the course:

- **Smart Data Broker:** core architecture, ingestion engine, routing logic — see [Vs Data Broker Overview](../productos/vs-data-broker-overview.md)
- **ETL (Extract, Transform, Load):** pipeline design and execution — see [Etl Pipeline](../conceptos/etl-pipeline.md)
- **Pipelines:** multi-source pipeline construction for IT, OT, and IoT data
- **Grid-handlers:** parsing, filtering, formatting, and modifying raw data streams in real-time
- **Plugin Creator:** building custom [Plugin Architecture](../conceptos/plugin-architecture.md) for non-standard data sources
- **Viewticore:** log normalization engine, data enrichment, and contextual annotation
- Ingestion protocols: [Syslog Extractor](../integraciones/syslog-extractor.md), [Snmp Extractor](../integraciones/snmp-extractor.md), [Netflow Extractor](../integraciones/netflow-extractor.md), [Rest Api](../productos/rest-api.md)

### 9. Advanced Troubleshooting

- Diagnostic tools and log inspection using [Cli Reference](../conceptos/cli-reference.md)
- Common ingestion failures and resolution procedures
- Pipeline debugging techniques
- Performance tuning for high-volume environments

---

## Assessment

After completing all agenda topics, participants deliver an Examination Presentation. A minimum score of 70% is required to earn the "Viewtinet Certified Data Engineer - VC DE" certificate.

## Related Pages

- [Vc De](../formacion/vc-de.md) — Course summary page
- [Vc Oa](../formacion/vc-oa.md) — Mandatory prerequisite
- [Vcoa Modules](vcoa-modules.md) — VCOA module breakdown
- [Viewtilog Overview](../productos/viewtilog-overview.md) — Core product reference
- [Viewtilog Installation](../instalacion/viewtilog-installation.md) — Installation guide
- [Training Overview](../formacion/training-overview.md) — Program overview
