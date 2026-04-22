---
tags: [cursos, vcoa, observabilidad]
tipo: tecnica
fuentes: ["portfolio-training-2026"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# VCOA Course — Detailed Module Breakdown

This page documents the six modules of the [[vc-oa]] (Viewtinet Certified Observability Analyst) course, including the theory vs. lab balance for each module.

## Overview

The [[vc-oa]] course runs 16 hours and is structured as a progressive journey from platform orientation to advanced automation. Modules 0 through 2 are pure theory; Modules 3 through 6 combine theory with hands-on lab sessions. This course is the mandatory analytical core and a prerequisite for [[vc-de]] and [[vc-wde]].

---

## Modules 0 & 1 — Welcome & Viewtinet Products (THEORY)

**Format:** Theory only

These opening modules orient participants to the course structure and provide a high-level overview of the entire Viewtinet suite:

- Course introduction, objectives, and assessment criteria
- Overview of all platform components: [[viewtisight-overview]], [[viewtilog-overview]], [[viewtimon-overview]], [[viewtiqos-overview]]
- The Viewtinet unified observability value proposition and "Single Pane of Glass" concept

---

## Module 2 — Architecture (THEORY)

**Format:** Theory only

Participants learn both the logical and physical architecture of the Viewtinet platform:

- **Logical architecture:** Control Plane vs. Data Plane separation
- **Physical architecture:** StandAlone, Cluster, and MSP (Managed Service Provider) deployment models — see [[standalone-vs-cluster]] and [[ha-architecture]]
- Introduction to [[viewtimanager-overview]] as the centralized control layer

---

## Module 3 — Viewtisight Immersion (THEORY | LAB)

**Format:** Theory + Lab

This module provides deep familiarity with the [[viewtisight-overview]] interface:

- GUI Navigation and Menu Structure — see [[gui-overview]]
- User Preferences and Favorites settings
- Data Anatomy: understanding how raw data is structured within [[viewtisight-overview]]
- Hierarchy between Data Sources and Dashboards

**Lab:** Participants navigate live environments, configure preferences, and explore data structures.

---

## Module 4 — Data Visualization (THEORY | LAB)

**Format:** Theory + Lab

Core metrics and visualization concepts are introduced:

- Raw Metrics vs. Dimensions: conceptual difference and practical implications
- **Metrics Composer:** building simple metrics using mathematical functions, then constructing complex, multi-layered metrics
- Chart Types and Card Builder basics: Aggregates, Time Series, and Map cards

**Lab:** Participants build metrics using the Composer and create their first visual cards.

---

## Module 5 — Building Dashboards (THEORY | LAB)

**Format:** Theory + Lab

Participants advance to full dashboard creation:

- Dashboard creation workflow and layout management
- HTML Cards for custom content embedding
- Global Filters and Drill-down navigation
- **Query Builder** for advanced data querying
- PDF Reporting for automated report generation — relevant for deployments at organizations like [[mapfre-usa]] or [[junta-andalucia]]

**Lab:** Participants design a complete operational dashboard with filters, drill-down, and a scheduled PDF report.

---

## Module 6 — Alarms & Notifications (THEORY | LAB)

**Format:** Theory + Lab

The final module covers the [[alarms-system]] in full:

- Alarm Panel navigation and management
- **Real-Time Alarms** vs. **Query-Based Alarms**: creation and configuration
- Rules, Thresholds, and Actions
- Notifications Log review
- Integrating external notifications (Teams, WhatsApp)
- Triggering automated actions: scripts and webhooks

**Lab:** Participants configure real-time and query-based alarms, define thresholds, and test webhook-triggered automations.

---

## Assessment

Completion of all six modules is followed by an Examination Presentation. A minimum score of 70% is required to earn the "Viewtinet Certified Observability Analyst - VC OA" certificate.

## Related Pages

- [[vc-oa]] — Course summary and enrollment information
- [[certification-paths]] — Where VCOA fits in the full certification structure
- [[vc-de-agenda]] — Next-level course agenda (requires VCOA)
- [[vc-wde-agenda]] — Alternative specialization after VCOA
