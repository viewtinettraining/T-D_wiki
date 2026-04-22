---
tags: [clientes, vc-lda]
tipo: tecnica
fuentes: ["cursos-projects-corpus"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Ministerio del Interior — VC-LDA

The Ministerio del Interior (Ministry of the Interior) of Spain is a central government ministry responsible for public security, border control, civil protection, and penitentiary services. It operates the national police (Policia Nacional), Guardia Civil, and associated critical infrastructure. This engagement is the VC-LDA (Data Engineer) delivery; a separate engagement under the VC-WDP (Wire Data) track is documented in [[ministerio-interior]].

## Course Delivered

The training delivered was [[vc-de]] (formerly VC-LDA — Certified Data Engineer), the 16-hour deep technical course requiring prior [[vc-oa]] certification. The engagement focuses on [[viewtilog-overview]] and [[viewtimanager-overview]] capabilities for large-scale network data engineering and observability in a security-critical environment.

## Training Materials

The project folder contains **1 PowerPoint presentation** and **1 CSV inventory file**:

| File | Description |
|---|---|
| MIN-INTERIOR.pptx | Customized course presentation |
| inventory_linux.csv | Linux system inventory export |

The `inventory_linux.csv` file is a significant artifact: it is an actual infrastructure inventory export from the client's Linux-based systems, likely generated via [[viewtimanager-overview]] [[autodiscovery]] or [[inventory-management]] functions, or provided as input data for a lab exercise.

## Notable Aspects

- **Linux inventory CSV**: This file represents real or simulated client infrastructure data, making it the only VC-LDA client folder with an operational data artifact (as opposed to the attendance CSV in [[jccm]]). It likely fed into [[viewtilog-overview]] pipeline or [[autodiscovery]] exercises.
- Security ministry environments require strict [[roles]] and [[users]] management, [[ldap-integration]] or [[active-directory]] integration, and potentially [[mfa-configuration]] — all covered in the [[vc-de-agenda]].
- The [[etl-pipeline]] and [[vs-data-broker-overview]] are relevant for aggregating security operations telemetry at scale.
- This client has two training engagements: this VC-LDA track and a separate [[ministerio-interior]] VC-WDP engagement covering [[viewtimon-overview]] and wire data analysis.

## Related Clients

[[ministerio-interior]] covers the same ministry's Wire Data training. Other public sector clients include [[ayto-madrid]], [[jccm]], [[junta-andalucia]]. The dual-track engagement (VC-LDA + VC-WDP) makes the Ministerio del Interior unique in the training corpus.
