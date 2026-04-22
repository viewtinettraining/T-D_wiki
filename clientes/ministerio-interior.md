---
tags: [clientes, vc-wdp]
tipo: tecnica
fuentes: ["cursos-projects-corpus"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Ministerio del Interior — VC-WDP

The Ministerio del Interior (Ministry of the Interior) of Spain is a central government ministry managing national security forces, border control, civil protection, and penitentiary infrastructure. This page documents the **Wire Data Engineer (VC-WDP)** training engagement. The ministry also received VC-LDA (Data Engineer) training, documented in [[mininterior-lda]].

## Course Delivered

The training delivered was [[vc-wde]] (formerly VC-WDP — Wire Data Engineer), the 8-hour course covering [[viewtimon-overview]], DPI traffic analysis, and wire data management. This is the most complete VC-WDP delivery in the corpus, with full dual-format materials (PDFs + PPTs) following the [[vc-wde-agenda]] completely.

## Training Materials

The project folder contains **7 PDFs** and **7 PPTs** (14 files total), making it the most comprehensive Wire Data training package:

| Module | PDF | PPT | Description |
|---|---|---|---|
| 01 | Yes | Yes | Welcome & Course Presentation |
| 02 | Yes | Yes | Viewtinet & Products |
| 03 | Yes | Yes | Deployment Mode |
| 04 | Yes | Yes | Viewtimanager |
| 05 | Yes | Yes | ViewtiMon |
| 06 | Yes | Yes | Viewtilog |
| 07 | Yes | Yes | ViewtiSight |

This 7-module set exceeds the standard [[vc-wde-agenda]], adding [[viewtilog-overview]] and [[viewtisight-overview]] modules not present in the [[gbo-balear]] 5-module package.

## Notable Aspects

- **Dual-format materials (PDF + PPT)**: The availability of both formats mirrors the [[giss]] and [[junta-andalucia]] approach in the VC-LDA track, suggesting a formal, structured training with pre-reading and instructor materials.
- **Extended 7-module set**: Including [[viewtilog-overview]] (module 06) and [[viewtisight-overview]] (module 07) in a Wire Data course is unusual and indicates cross-track training — exposing attendees to [[etl-pipeline]] and analytics capabilities beyond standard VC-WDP scope.
- **Deployment Mode module** covers inline vs. sniffer deployment for [[viewtimon-overview]] and [[viewtiqos-overview]], including [[standalone-vs-cluster]] considerations.
- [[viewtimanager-overview]] content covers [[inventory-management]], [[autodiscovery]], [[users]], [[roles]], and [[tenants]] for enterprise-scale security infrastructure.
- The ministry's dual-track engagement (VC-LDA + VC-WDP) is unique in the entire training corpus.

## Related Clients

[[mininterior-lda]] covers the same ministry's Data Engineer training. [[gbo-balear]] is the other VC-WDP client. Public sector peers include [[ayto-madrid]], [[jccm]], and [[junta-andalucia]].
