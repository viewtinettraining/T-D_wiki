---
tags: [clientes, vc-lda]
tipo: tecnica
fuentes: ["cursos-projects-corpus"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# MAPFRE USA

MAPFRE USA is the North American subsidiary of MAPFRE, one of Spain's largest insurance groups and a major global insurer. Operating in the United States insurance market, MAPFRE USA manages IT infrastructure supporting claims processing, policy management, and regulatory compliance — environments where network observability and data engineering are critical.

## Course Delivered

The training delivered was [[vc-de]] (formerly VC-LDA — Certified Data Engineer), the full 16-hour course. Students must hold [[vc-oa]] certification as a prerequisite. With 9 modules, MAPFRE USA received one of the most complete VC-LDA PPT-only deliveries in the corpus, second only to [[giss]] which also includes PDFs and a workbook.

## Training Materials

The project folder contains **9 PowerPoint presentations** (in a `PPTS/` subfolder):

| Module | Description |
|---|---|
| 01 | Welcome & Course Presentation |
| 02 | Viewtinet & Products |
| 03 | Software Architecture |
| 04 | Deployment Mode |
| 05 | Viewtiauth |
| 06 | Viewtimanager |
| 07 | LAB Access |
| 08 | Viewtilog |
| 09 | ViewtiSight |

This is the fullest PPT-only VC-LDA set in the corpus, following the [[vc-de-agenda]] completely.

## Notable Aspects

- **Viewtiauth module** (module 05) covers [[ldap-integration]], [[active-directory]], [[mfa-configuration]], and authentication backend configuration — essential for enterprise insurance environments with strict identity governance.
- **Deployment Mode module** covers [[standalone-vs-cluster]] decisions and [[ha-architecture]] for high-availability deployments, critical for financial sector SLA requirements.
- **LAB Access module** provides hands-on access to the Viewtinet environment, supporting the practical component of the [[vc-de-agenda]].
- [[viewtimanager-overview]] covers [[users]], [[roles]], [[tenants]], and [[autodiscovery]] for enterprise multi-site management.
- [[viewtilog-overview]] and [[vs-data-broker-overview]] address the [[etl-pipeline]] capabilities for processing insurance data flows and network telemetry.
- The US-based location of this client reflects Viewtinet's international commercial reach.

## Related Clients

[[giss]] is the closest peer, also receiving a full module set with Viewtiauth. [[junta-andalucia]] shares the theory/practice depth. Within the financial/enterprise sector, MAPFRE USA stands alone among VC-LDA clients.
