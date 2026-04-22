---
tags: [cursos, vc-wde, viewtimon, viewtiqos]
tipo: tecnica
fuentes: ["portfolio-training-2026"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# VC-WDE Detailed Agenda

This page documents the full agenda of the [[vc-wde]] (Viewtinet Wire Data Engineer / VC-WDP) course, covering hardware, deployment modes (Sniffer and Inline), [[viewtimon-overview]], and [[viewtiqos-overview]] practical sessions.

## Prerequisites Reminder

Participants must have basic knowledge of the Linux terminal before enrolling. While [[vc-oa]] is not a strict prerequisite for VC-WDE, familiarity with the Viewtinet platform and [[viewtisight-overview]] dashboards is highly beneficial.

---

## Agenda Topics

### 1. Welcome and Course Introduction

- Course objectives and structure
- Assessment criteria: 70% minimum score on examination presentation
- Introduction to the ViewtiMon & Viewtify vertical within [[certification-paths]]

### 2. Viewtinet Products

- High-level review of the full platform: [[viewtisight-overview]], [[viewtilog-overview]], [[viewtimon-overview]], [[viewtiqos-overview]]
- Focus positioning: how [[viewtimon-overview]] and [[viewtiqos-overview]] relate to the broader suite

### 3. Architecture and Software Structure

- Logical architecture: Control Plane vs. Data Plane separation
- Physical deployment models: StandAlone, Cluster — see [[standalone-vs-cluster]]
- [[ha-architecture]] considerations for ViewtiMon deployments
- Data flow from capture point to [[viewtisight-overview]] dashboards

### 4. Hardware: Appliances and Bypass

- Appliance models and technical specifications for network monitoring use cases
- **Bypass modules:** purpose, configuration, and failsafe behavior in Inline deployments
- Network interface card (NIC) compatibility and certified configurations
- Rack installation and cabling best practices

### 5. Deployment Modes

This is a key differentiating section of VC-WDE:

- **Sniffer (passive):** captures traffic via SPAN/mirror port; zero impact on production traffic flow; ideal for visibility-only use cases
- **Inline (active):** device sits directly in the traffic path; enables real-time [[viewtiqos-overview]] policy enforcement including rate limiting and traffic prioritization
- Decision criteria for selecting the appropriate deployment mode per environment
- Relevant for large-scale deployments such as those at [[gbo-balear]] or [[ministerio-interior]]

### 6. Installation (Practical Session)

- Step-by-step [[viewtimon-installation]] procedures
- Licensing and initial platform configuration
- OS setup requirements — see [[os-setup]] and [[ubuntu-compatibility]]
- Network interface assignment and validation

### 7. Viewtimanager

- GUI overview and component navigation — see [[viewtimanager-overview]] and [[gui-overview]]
- User and role management — see [[users]] and [[roles]]
- [[inventory-management]] and [[autodiscovery]] for discovered network devices
- Integration with [[ldap-integration]] or [[active-directory]] for enterprise environments

### 8. ViewtiMon — Theory and Lab

- DPI (Deep Packet Inspection) engine fundamentals
- Traffic collection: understanding what [[viewtimon-overview]] captures and how
- Metrics and Dimensions: raw network data vs. aggregated metrics
- Creating and customizing dashboards in [[viewtisight-overview]] for network visibility
- Configuring the [[alarms-system]]: defining metric thresholds and email notification rules

**Lab:** Participants connect to a live ViewtiMon instance, explore captured traffic metrics, and build a network performance dashboard.

### 9. ViewtifyQoS (Practical Session)

- Traffic prioritization concepts and policy management using [[viewtiqos-overview]]
- Profile creation: classifying traffic by origin, application, or application group
- Applying rate limiting and prioritization rules
- Deployment options for QoS policy enforcement in Inline mode
- Infrastructure requirements for effective QoS

**Lab:** Participants create traffic profiles, define QoS policies, and validate enforcement through dashboard metrics.

### 10. Troubleshooting

- Common deployment issues: interface detection, traffic capture failures, licensing errors
- Diagnostic commands using [[cli-reference]]
- Log inspection and error analysis
- Escalation procedures and support resources

---

## Assessment

After completing all agenda topics, participants deliver an Examination Presentation. A minimum score of 70% is required to earn the "Viewtinet Certified Wire Data Professional - VC WDP" certificate.

## Related Pages

- [[vc-wde]] — Course summary page
- [[viewtimon-overview]] — Core product reference
- [[viewtiqos-overview]] — Traffic management product reference
- [[viewtimon-installation]] — Installation guide
- [[vcoa-modules]] — VCOA modules (beneficial background)
- [[training-overview]] — Program overview
