---
tags: [formacion, certificacion, data-engineering]
tipo: tecnica
fuentes: ["portfolio-training-2026"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# VC-DE — Viewtinet Certified Data Engineer

The VC-DE (Viewtinet Certified Data Engineer) is the advanced specialization for professionals focused on data integration, log management, and pipeline engineering using [[viewtilog-overview]]. It was previously known as **VC-LDA** (Level Deep Analysis) in older course catalogs.

## Course Details

| Field | Value |
|---|---|
| Duration | 16 hours |
| Delivery | Online and on-site |
| Target audience | Network, systems, and data engineers from end customers and partners |
| Prerequisites | **[[vc-oa]] certification is STRICTLY REQUIRED** |
| Assessment | Examination Presentation (minimum 70%) |
| Certification | "Viewtinet Certified Data Engineer - VC DE" |

## Overview

The VC-DE is a specialized technical vertical focused entirely on data integration and log management. Participants master the **Smart Data Broker** architecture within [[viewtilog-overview]], execute multi-source ingestion from IT, OT, and IoT environments, and use Grid-handlers for advanced data transformation following the [[etl-pipeline]] model. Log normalization and enrichment are also core competencies.

## Learning Objectives

- **Viewtilog Architecture Mastery:** Understand core components of the Smart Data Broker and Viewticore to design efficient data pipelines; see [[vs-data-broker-overview]]
- **Multi-Source Ingestion:** Integrate and collect data from diverse IT, OT, and IoT environments using protocols including Syslog ([[syslog-extractor]]), SNMP ([[snmp-extractor]]), and API ([[rest-api]])
- **Data Transformation (ETL):** Master Grid-handlers to parse, filter, format, and modify raw data streams in real-time following [[etl-pipeline]] principles
- **Normalization & Enrichment:** Standardize unstructured logs into normalized formats and enrich data with contextual information using [[plugin-architecture]]

## Agenda

The full topic-by-topic agenda is documented in [[vc-de-agenda]]. Key sections include:

1. Welcome and Course Introduction
2. Viewtinet Products overview
3. Architecture and Software Structure
4. Viewtinet Hardware Portfolio
5. Bundle Installation (Practical Session) — see [[installation-bundle]]
6. Viewtiauth — Authentication types; see [[users]] and [[roles]]
7. **Viewtimanager** — GUI & Components, Self-Monitoring, External Service Integration (SMTP / [[ldap-integration]]), User/Group/Role Management, [[tenants]], [[inventory-management]], [[autodiscovery]]
8. **Viewtilog** — Smart Data Broker, ETL, Pipelines, Plugin Creator, Viewticore
9. Advanced Troubleshooting

## Prerequisites Note

Enrollment is blocked without a valid [[vc-oa]] certification. This requirement ensures all participants arrive with proficiency in [[viewtisight-overview]] navigation, metrics construction, and dashboard design before diving into the data engineering layer.

## Formerly VC-LDA

In older Viewtinet course catalogs this course was listed as **VC-LDA** (Level Deep Analysis). Partners and customers migrating from historical training programs should map VC-LDA records to VC-DE for continuity.

## Position in the Certification Path

VC-DE is part of the Viewtilog vertical. See [[certification-paths]] for the full structure and progression flow.

## Related Pages

- [[vc-oa]] — Mandatory prerequisite
- [[vc-de-agenda]] — Full detailed agenda
- [[viewtilog-overview]] — Product covered in depth
- [[viewtilog-installation]] — Installation reference
- [[training-overview]] — Program overview
