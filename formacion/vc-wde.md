---
tags: [formacion, certificacion, network-monitoring]
tipo: tecnica
fuentes: ["portfolio-training-2026"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# VC-WDE — Viewtinet Wire Data Engineer (VC-WDP)

The VC-WDE (Viewtinet Wire Data Engineer), also referred to as **VC-WDP** (Wire Data Professional) in some documentation, is the specialization track for professionals managing network traffic visibility and bandwidth control using [[viewtimon-overview]] and [[viewtiqos-overview]].

## Course Details

| Field | Value |
|---|---|
| Duration | 8 hours |
| Delivery | Online and on-site |
| Target audience | IT professionals specializing in Viewtinet observability and traffic management |
| Prerequisites | Basic knowledge of the Linux terminal |
| Assessment | Examination Presentation (minimum 70%) |
| Certification | "Viewtinet Certified Wire Data Professional - VC WDP" |

## Overview

The VC-WDE equips professionals with the skills required to install, configure, integrate, and manage [[viewtimon-overview]] and [[viewtiqos-overview]] in production environments. A central focus is **deep packet inspection (DPI)** for effective bandwidth management. Participants also learn to create and manage dashboards and alerts to monitor network performance.

## Learning Objectives

- **Understanding the Viewtinet Platform:** Architecture and functionalities for data collection, storage, and analysis using [[viewtimon-overview]]
- **Installation and Configuration:** Procedures for installing, licensing, and setting up the ViewtiMon / ViewtifyQoS product; see [[viewtimon-installation]]
- **Profiles and Policies:** Classify traffic by origin, application, or application group; apply rate limiting or traffic prioritization using [[viewtiqos-overview]]
- **Metrics and Visualization:** Understand metrics and dimensions, create and customize dashboards in [[viewtisight-overview]]
- **Alarm Management:** Define metric thresholds and generate email notifications through the [[alarms-system]]

## Agenda

The detailed topic-by-topic breakdown is documented in [[vc-wde-agenda]]. Key sections include:

1. Welcome and Course Introduction
2. Viewtinet Products overview
3. Architecture and Software Structure — see [[standalone-vs-cluster]]
4. Hardware: Appliances and Bypass
5. Deployment Modes: **Sniffer** and **Inline**
6. Installation (Practical Session)
7. Viewtimanager — see [[viewtimanager-overview]] and [[gui-overview]]
8. ViewtiMon (theory and lab) — see [[viewtimon-overview]]
9. ViewtifyQoS (Practical Session) — see [[viewtiqos-overview]]
10. Troubleshooting — see [[cli-reference]]

## Prerequisites Note

Unlike [[vc-de]], the VC-WDE does not strictly require [[vc-oa]] as a formal prerequisite, but basic Linux terminal proficiency is required. In practice, familiarity with the Viewtinet platform from [[vc-oa]] is highly beneficial.

## Deployment Modes: Sniffer vs Inline

A key differentiator of this course is the coverage of both deployment modes:

- **Sniffer (passive):** Captures traffic from a span/mirror port without affecting traffic flow
- **Inline (active):** Sits directly in the traffic path, enabling active [[viewtiqos-overview]] enforcement

## Certification Name Note

The certificate issued is titled "Viewtinet Certified Wire Data Professional - VC WDP," even though the course is also commonly referred to as VC-WDE. Both names refer to the same program. Organizations such as [[gbo-balear]] may have staff with either designation in their training records.

## Position in the Certification Path

VC-WDE is part of the ViewtiMon & Viewtify vertical. See [[certification-paths]] for the full map.

## Related Pages

- [[vc-wde-agenda]] — Full detailed agenda
- [[viewtimon-overview]] — Core product covered
- [[viewtiqos-overview]] — Traffic management product covered
- [[training-overview]] — Program overview
- [[certification-paths]] — Full certification structure
