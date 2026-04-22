---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'VC-WDE Detailed Agenda'
id: WIU-SSV-PI7-VII
slug: vc-wde-agenda
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# VC-WDE Detailed Agenda

This page documents the full agenda of the [Vc Wde](../formacion/vc-wde.md) (Viewtinet Wire Data Engineer / VC-WDP) course, covering hardware, deployment modes (Sniffer and Inline), [Viewtimon Overview](../productos/viewtimon-overview.md), and [Viewtiqos Overview](../productos/viewtiqos-overview.md) practical sessions.

## Prerequisites Reminder

Participants must have basic knowledge of the Linux terminal before enrolling. While [Vc Oa](../formacion/vc-oa.md) is not a strict prerequisite for VC-WDE, familiarity with the Viewtinet platform and [Viewtisight Overview](../productos/viewtisight-overview.md) dashboards is highly beneficial.

---

## Agenda Topics

### 1. Welcome and Course Introduction

- Course objectives and structure
- Assessment criteria: 70% minimum score on examination presentation
- Introduction to the ViewtiMon & Viewtify vertical within [Certification Paths](../formacion/certification-paths.md)

### 2. Viewtinet Products

- High-level review of the full platform: [Viewtisight Overview](../productos/viewtisight-overview.md), [Viewtilog Overview](../productos/viewtilog-overview.md), [Viewtimon Overview](../productos/viewtimon-overview.md), [Viewtiqos Overview](../productos/viewtiqos-overview.md)
- Focus positioning: how [Viewtimon Overview](../productos/viewtimon-overview.md) and [Viewtiqos Overview](../productos/viewtiqos-overview.md) relate to the broader suite

### 3. Architecture and Software Structure

- Logical architecture: Control Plane vs. Data Plane separation
- Physical deployment models: StandAlone, Cluster — see [Standalone Vs Cluster](../conceptos/standalone-vs-cluster.md)
- [Ha Architecture](../conceptos/ha-architecture.md) considerations for ViewtiMon deployments
- Data flow from capture point to [Viewtisight Overview](../productos/viewtisight-overview.md) dashboards

### 4. Hardware: Appliances and Bypass

- Appliance models and technical specifications for network monitoring use cases
- **Bypass modules:** purpose, configuration, and failsafe behavior in Inline deployments
- Network interface card (NIC) compatibility and certified configurations
- Rack installation and cabling best practices

### 5. Deployment Modes

This is a key differentiating section of VC-WDE:

- **Sniffer (passive):** captures traffic via SPAN/mirror port; zero impact on production traffic flow; ideal for visibility-only use cases
- **Inline (active):** device sits directly in the traffic path; enables real-time [Viewtiqos Overview](../productos/viewtiqos-overview.md) policy enforcement including rate limiting and traffic prioritization
- Decision criteria for selecting the appropriate deployment mode per environment
- Relevant for large-scale deployments such as those at [Gbo Balear](../clientes/gbo-balear.md) or [Ministerio Interior](../clientes/ministerio-interior.md)

### 6. Installation (Practical Session)

- Step-by-step [Viewtimon Installation](../instalacion/viewtimon-installation.md) procedures
- Licensing and initial platform configuration
- OS setup requirements — see [Os Setup](../instalacion/os-setup.md) and [Ubuntu Compatibility](../conceptos/ubuntu-compatibility.md)
- Network interface assignment and validation

### 7. Viewtimanager

- GUI overview and component navigation — see [Viewtimanager Overview](../productos/viewtimanager-overview.md) and [Gui Overview](../configuracion/gui-overview.md)
- User and role management — see [Users](../configuracion/users.md) and [Roles](../configuracion/roles.md)
- [Inventory Management](../configuracion/inventory-management.md) and [Autodiscovery](../configuracion/autodiscovery.md) for discovered network devices
- Integration with [Ldap Integration](../integraciones/ldap-integration.md) or [Active Directory](../integraciones/active-directory.md) for enterprise environments

### 8. ViewtiMon — Theory and Lab

- DPI (Deep Packet Inspection) engine fundamentals
- Traffic collection: understanding what [Viewtimon Overview](../productos/viewtimon-overview.md) captures and how
- Metrics and Dimensions: raw network data vs. aggregated metrics
- Creating and customizing dashboards in [Viewtisight Overview](../productos/viewtisight-overview.md) for network visibility
- Configuring the [Alarms System](../conceptos/alarms-system.md): defining metric thresholds and email notification rules

**Lab:** Participants connect to a live ViewtiMon instance, explore captured traffic metrics, and build a network performance dashboard.

### 9. ViewtifyQoS (Practical Session)

- Traffic prioritization concepts and policy management using [Viewtiqos Overview](../productos/viewtiqos-overview.md)
- Profile creation: classifying traffic by origin, application, or application group
- Applying rate limiting and prioritization rules
- Deployment options for QoS policy enforcement in Inline mode
- Infrastructure requirements for effective QoS

**Lab:** Participants create traffic profiles, define QoS policies, and validate enforcement through dashboard metrics.

### 10. Troubleshooting

- Common deployment issues: interface detection, traffic capture failures, licensing errors
- Diagnostic commands using [Cli Reference](../conceptos/cli-reference.md)
- Log inspection and error analysis
- Escalation procedures and support resources

---

## Assessment

After completing all agenda topics, participants deliver an Examination Presentation. A minimum score of 70% is required to earn the "Viewtinet Certified Wire Data Professional - VC WDP" certificate.

## Related Pages

- [Vc Wde](../formacion/vc-wde.md) — Course summary page
- [Viewtimon Overview](../productos/viewtimon-overview.md) — Core product reference
- [Viewtiqos Overview](../productos/viewtiqos-overview.md) — Traffic management product reference
- [Viewtimon Installation](../instalacion/viewtimon-installation.md) — Installation guide
- [Vcoa Modules](vcoa-modules.md) — VCOA modules (beneficial background)
- [Training Overview](../formacion/training-overview.md) — Program overview
