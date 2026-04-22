---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'VCOA Course — Detailed Module Breakdown'
id: JC6-UUY-DS1-3HC
slug: vcoa-modules
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# VCOA Course — Detailed Module Breakdown

This page documents the six modules of the [Vc Oa](../formacion/vc-oa.md) (Viewtinet Certified Observability Analyst) course, including the theory vs. lab balance for each module.

## Overview

The [Vc Oa](../formacion/vc-oa.md) course runs 16 hours and is structured as a progressive journey from platform orientation to advanced automation. Modules 0 through 2 are pure theory; Modules 3 through 6 combine theory with hands-on lab sessions. This course is the mandatory analytical core and a prerequisite for [Vc De](../formacion/vc-de.md) and [Vc Wde](../formacion/vc-wde.md).

---

## Modules 0 & 1 — Welcome & Viewtinet Products (THEORY)

**Format:** Theory only

These opening modules orient participants to the course structure and provide a high-level overview of the entire Viewtinet suite:

- Course introduction, objectives, and assessment criteria
- Overview of all platform components: [Viewtisight Overview](../productos/viewtisight-overview.md), [Viewtilog Overview](../productos/viewtilog-overview.md), [Viewtimon Overview](../productos/viewtimon-overview.md), [Viewtiqos Overview](../productos/viewtiqos-overview.md)
- The Viewtinet unified observability value proposition and "Single Pane of Glass" concept

---

## Module 2 — Architecture (THEORY)

**Format:** Theory only

Participants learn both the logical and physical architecture of the Viewtinet platform:

- **Logical architecture:** Control Plane vs. Data Plane separation
- **Physical architecture:** StandAlone, Cluster, and MSP (Managed Service Provider) deployment models — see [Standalone Vs Cluster](../conceptos/standalone-vs-cluster.md) and [Ha Architecture](../conceptos/ha-architecture.md)
- Introduction to [Viewtimanager Overview](../productos/viewtimanager-overview.md) as the centralized control layer

---

## Module 3 — Viewtisight Immersion (THEORY | LAB)

**Format:** Theory + Lab

This module provides deep familiarity with the [Viewtisight Overview](../productos/viewtisight-overview.md) interface:

- GUI Navigation and Menu Structure — see [Gui Overview](../configuracion/gui-overview.md)
- User Preferences and Favorites settings
- Data Anatomy: understanding how raw data is structured within [Viewtisight Overview](../productos/viewtisight-overview.md)
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
- PDF Reporting for automated report generation — relevant for deployments at organizations like [Mapfre Usa](../clientes/mapfre-usa.md) or [Junta Andalucia](../clientes/junta-andalucia.md)

**Lab:** Participants design a complete operational dashboard with filters, drill-down, and a scheduled PDF report.

---

## Module 6 — Alarms & Notifications (THEORY | LAB)

**Format:** Theory + Lab

The final module covers the [Alarms System](../conceptos/alarms-system.md) in full:

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

- [Vc Oa](../formacion/vc-oa.md) — Course summary and enrollment information
- [Certification Paths](../formacion/certification-paths.md) — Where VCOA fits in the full certification structure
- [Vc De Agenda](vc-de-agenda.md) — Next-level course agenda (requires VCOA)
- [Vc Wde Agenda](vc-wde-agenda.md) — Alternative specialization after VCOA
