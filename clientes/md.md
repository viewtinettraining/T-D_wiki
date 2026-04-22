---
title: "MD"
description: "MD is a client in the Viewtinet VC-LDA training program. The exact organization name behind the \"MD\" project code is not specified in the available materials..."
keywords: "clientes, vc-lda"
---

# MD

MD is a client in the Viewtinet VC-LDA training program. The exact organization name behind the "MD" project code is not specified in the available materials. Based on the training content — particularly the inclusion of a dedicated **Hardware module** — MD is likely a technical integrator, managed service provider, or internal Viewtinet team receiving comprehensive pre-deployment training.

## Course Delivered

The training delivered was [Vc De](../formacion/vc-de.md) (formerly VC-LDA — Certified Data Engineer), the 16-hour technical course. Prior [Vc Oa](../formacion/vc-oa.md) certification is required. The MD project is notable for including a hardware-focused module not present in other client packages, suggesting a hands-on infrastructure deployment context rather than a pure software operations engagement.

## Training Materials

The project folder contains **7 PowerPoint presentations**:

| Module | Description |
|---|---|
| 01 | Introduction |
| 02 | Products |
| 03 | Software Architecture |
| 03 | Architecture & Deployment Modes (second module 03) |
| 04 | Hardware |
| 05 | Viewtimanager |
| 06 | Viewtilog |
| 07 | ViewtiSight |

Note: Two files share the `03` prefix — `03 Software Architecture.pptx` and `03-Architecture & Deployment Modes.pptx` — indicating an extended architecture section split across two presentations, likely reflecting a deep-dive into [Standalone Vs Cluster](../conceptos/standalone-vs-cluster.md) and [Ha Architecture](../conceptos/ha-architecture.md) decisions.

## Notable Aspects

- **Hardware module** (04-Hardware.pptx): This is unique across all VC-LDA client deliveries and covers physical appliance specs, racking, NIC selection, and potentially [Ipmi Management](../conceptos/ipmi-management.md) — content typically found in the [Installation Bundle](../instalacion/installation-bundle.md) documentation rather than standard course slides.
- The dual Architecture module suggests thorough coverage of [Standalone Vs Cluster](../conceptos/standalone-vs-cluster.md) deployment modes and physical vs. virtual deployment considerations.
- [Viewtimanager Overview](../productos/viewtimanager-overview.md) content covers [Autodiscovery](../configuracion/autodiscovery.md), [Inventory Management](../configuracion/inventory-management.md), [Users](../configuracion/users.md), [Roles](../configuracion/roles.md), and [Tenants](../configuracion/tenants.md).
- [Viewtilog Overview](../productos/viewtilog-overview.md) and [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) address [Etl Pipeline](../conceptos/etl-pipeline.md) pipeline construction.
- The Introduction + Products format (rather than a combined Welcome module) mirrors the [Cepsa](cepsa.md) delivery structure.

## Related Clients

[Mapfre Usa](mapfre-usa.md) and [Giss](giss.md) are the other VC-LDA clients with full multi-module sets. MD is unique in including hardware content, making it most similar to an internal or pre-sales technical training scenario.
