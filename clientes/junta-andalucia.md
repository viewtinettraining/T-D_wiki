---
tags: [clientes, vc-lda]
tipo: tecnica
fuentes: ["cursos-projects-corpus"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Junta de Andalucia

The Junta de Andalucia is the regional government of Andalusia, the most populous autonomous community in Spain. It manages one of the largest public IT infrastructures in the country, covering health (SAS), education, justice, and social services. This engagement is notable because it was delivered through **Telefonica** as a channel partner.

## Course Delivered

The training delivered was [[vc-de]] (formerly VC-LDA — Certified Data Engineer), the 16-hour technical course. Prior [[vc-oa]] certification is a prerequisite. This is the most comprehensive PDF-based VC-LDA delivery in the corpus, with separate Theory (T) and Practice (P) modules for key products — aligning with a structured, examination-grade course format per the [[vc-de-agenda]].

## Training Materials

The project folder contains **11 PDFs** (in a `PDFs/` subfolder) and **1 PPT** (in a `Telefonica/` subfolder):

| Module | Type | Description |
|---|---|---|
| 01-T | PDF | Welcome & Course Presentation |
| 02-T | PDF | Viewtinet & Products |
| 03-T | PDF | Software Architecture |
| 04-T | PDF | Architecture & Deployment Modes |
| 06-T | PDF | Viewtimanager (Theory) |
| 07-P | PDF | Viewtimanager (Practice) |
| 08-T | PDF | Viewtilog (Theory) |
| 09-P | PDF | Viewtilog + VSDB (Practice) |
| 10-T | PDF | ViewtiSight (Theory) |
| 11-P | PDF | ViewtiSight (Practice) |
| JdA.pptx | PPT | Telefonica channel partner presentation |

Note: Module 05 is absent from the PDF set, suggesting a possible LAB Access or Viewtiauth module was handled separately or omitted.

## Notable Aspects

- **Delivered via Telefonica**: The `Telefonica/` subfolder and `JdA.pptx` file indicate this training was coordinated through Telefonica as a reseller or system integrator partner — the only such channel delivery in the VC-LDA corpus.
- **Theory + Practice split**: Separate T/P modules for [[viewtimanager-overview]], [[viewtilog-overview]], and [[viewtisight-overview]] indicate a lab-intensive delivery style.
- The Practice Viewtilog module (`09-P-Viewtilog-VSDB`) explicitly covers the [[vs-data-broker-overview]], including [[etl-pipeline]] construction.
- [[standalone-vs-cluster]] and [[ha-architecture]] are covered in the Architecture & Deployment Modes module.
- [[autodiscovery]], [[inventory-management]], [[roles]], and [[tenants]] are addressed in the Viewtimanager modules.

## Related Clients

Other Spanish public administration clients include [[ayto-madrid]], [[jccm]], [[mininterior-lda]], and [[ministerio-interior]]. The partner-delivered format is unique to this engagement.
