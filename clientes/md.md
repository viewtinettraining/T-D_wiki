---
tags: [clientes, vc-lda]
tipo: tecnica
fuentes: ["cursos-projects-corpus"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# MD

MD is a client in the Viewtinet VC-LDA training program. The exact organization name behind the "MD" project code is not specified in the available materials. Based on the training content — particularly the inclusion of a dedicated **Hardware module** — MD is likely a technical integrator, managed service provider, or internal Viewtinet team receiving comprehensive pre-deployment training.

## Course Delivered

The training delivered was [[vc-de]] (formerly VC-LDA — Certified Data Engineer), the 16-hour technical course. Prior [[vc-oa]] certification is required. The MD project is notable for including a hardware-focused module not present in other client packages, suggesting a hands-on infrastructure deployment context rather than a pure software operations engagement.

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

Note: Two files share the `03` prefix — `03 Software Architecture.pptx` and `03-Architecture & Deployment Modes.pptx` — indicating an extended architecture section split across two presentations, likely reflecting a deep-dive into [[standalone-vs-cluster]] and [[ha-architecture]] decisions.

## Notable Aspects

- **Hardware module** (04-Hardware.pptx): This is unique across all VC-LDA client deliveries and covers physical appliance specs, racking, NIC selection, and potentially [[ipmi-management]] — content typically found in the [[installation-bundle]] documentation rather than standard course slides.
- The dual Architecture module suggests thorough coverage of [[standalone-vs-cluster]] deployment modes and physical vs. virtual deployment considerations.
- [[viewtimanager-overview]] content covers [[autodiscovery]], [[inventory-management]], [[users]], [[roles]], and [[tenants]].
- [[viewtilog-overview]] and [[vs-data-broker-overview]] address [[etl-pipeline]] pipeline construction.
- The Introduction + Products format (rather than a combined Welcome module) mirrors the [[cepsa]] delivery structure.

## Related Clients

[[mapfre-usa]] and [[giss]] are the other VC-LDA clients with full multi-module sets. MD is unique in including hardware content, making it most similar to an internal or pre-sales technical training scenario.
