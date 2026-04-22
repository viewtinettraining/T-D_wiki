---
tags: [cursos, vc-de, viewtilog]
tipo: tecnica
fuentes: ["portfolio-training-2026"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# VC-DE Detailed Agenda

This page documents the full agenda of the [[vc-de]] (Viewtinet Certified Data Engineer) course, including all topics, the Viewtimanager coverage section, and the Viewtilog deep dive.

## Prerequisites Reminder

**[[vc-oa]] certification is strictly required** before enrolling in VC-DE. Participants without VCOA will not be admitted. This ensures all engineers arrive with proficiency in [[viewtisight-overview]], the Metrics Composer, and the [[alarms-system]].

---

## Agenda Topics

### 1. Welcome and Course Introduction

- Course objectives and assessment criteria (70% minimum on examination presentation)
- Overview of the Viewtinet certification path — see [[certification-paths]]
- Logistics and lab environment access

### 2. Viewtinet Products

- High-level review of the full suite: [[viewtisight-overview]], [[viewtilog-overview]], [[viewtimon-overview]], [[viewtiqos-overview]]
- Relationship between components and the role of [[viewtimanager-overview]]

### 3. Architecture and Software Structure

- Logical architecture: Control Plane vs. Data Plane
- Physical deployment options: StandAlone, Cluster, MSP — see [[standalone-vs-cluster]] and [[ha-architecture]]
- Software bundle structure and component interaction

### 4. Viewtinet Hardware Portfolio

- Appliance models, technical specifications, and best-fit scenarios
- Hardware selection based on traffic volume, user base, and data retention requirements

### 5. Bundle Installation (Practical Session)

- Step-by-step [[installation-bundle]] process
- OS prerequisites — see [[os-setup]] and [[ubuntu-compatibility]]
- [[viewtilog-installation]] procedures and initial validation

### 6. Viewtiauth

- Authentication architecture overview
- Authentication types: local, [[ldap-integration]], [[active-directory]]
- Token and session management

### 7. Viewtimanager — Deep Coverage

The Viewtimanager section is one of the most extensive in VC-DE:

- GUI & Components overview — see [[viewtimanager-overview]] and [[gui-overview]]
- Self-Monitoring: platform health visibility
- Integration with External Services: SMTP configuration, [[ldap-integration]]
- **User, Group, and Role Management** — see [[users]] and [[roles]]
- **Tenants** — multi-tenant configuration for MSP deployments — see [[tenants]]
- [[inventory-management]] — device registration and asset tracking
- [[autodiscovery]] — automatic device detection and onboarding

### 8. Viewtilog — Deep Dive

This is the central technical section of the course:

- **Smart Data Broker:** core architecture, ingestion engine, routing logic — see [[vs-data-broker-overview]]
- **ETL (Extract, Transform, Load):** pipeline design and execution — see [[etl-pipeline]]
- **Pipelines:** multi-source pipeline construction for IT, OT, and IoT data
- **Grid-handlers:** parsing, filtering, formatting, and modifying raw data streams in real-time
- **Plugin Creator:** building custom [[plugin-architecture]] for non-standard data sources
- **Viewticore:** log normalization engine, data enrichment, and contextual annotation
- Ingestion protocols: [[syslog-extractor]], [[snmp-extractor]], [[netflow-extractor]], [[rest-api]]

### 9. Advanced Troubleshooting

- Diagnostic tools and log inspection using [[cli-reference]]
- Common ingestion failures and resolution procedures
- Pipeline debugging techniques
- Performance tuning for high-volume environments

---

## Assessment

After completing all agenda topics, participants deliver an Examination Presentation. A minimum score of 70% is required to earn the "Viewtinet Certified Data Engineer - VC DE" certificate.

## Related Pages

- [[vc-de]] — Course summary page
- [[vc-oa]] — Mandatory prerequisite
- [[vcoa-modules]] — VCOA module breakdown
- [[viewtilog-overview]] — Core product reference
- [[viewtilog-installation]] — Installation guide
- [[training-overview]] — Program overview
