---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Ministerio del Interior — VC-LDA'
id: 56M-7OE-ZRF-3AA
slug: mininterior-lda
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Ministerio del Interior — VC-LDA

The Ministerio del Interior (Ministry of the Interior) of Spain is a central government ministry responsible for public security, border control, civil protection, and penitentiary services. It operates the national police (Policia Nacional), Guardia Civil, and associated critical infrastructure. This engagement is the VC-LDA (Data Engineer) delivery; a separate engagement under the VC-WDP (Wire Data) track is documented in [Ministerio Interior](ministerio-interior.md).

## Course Delivered

The training delivered was [Vc De](../formacion/vc-de.md) (formerly VC-LDA — Certified Data Engineer), the 16-hour deep technical course requiring prior [Vc Oa](../formacion/vc-oa.md) certification. The engagement focuses on [Viewtilog Overview](../productos/viewtilog-overview.md) and [Viewtimanager Overview](../productos/viewtimanager-overview.md) capabilities for large-scale network data engineering and observability in a security-critical environment.

## Training Materials

The project folder contains **1 PowerPoint presentation** and **1 CSV inventory file**:

| File | Description |
|---|---|
| MIN-INTERIOR.pptx | Customized course presentation |
| inventory_linux.csv | Linux system inventory export |

The `inventory_linux.csv` file is a significant artifact: it is an actual infrastructure inventory export from the client's Linux-based systems, likely generated via [Viewtimanager Overview](../productos/viewtimanager-overview.md) [Autodiscovery](../configuracion/autodiscovery.md) or [Inventory Management](../configuracion/inventory-management.md) functions, or provided as input data for a lab exercise.

## Notable Aspects

- **Linux inventory CSV**: This file represents real or simulated client infrastructure data, making it the only VC-LDA client folder with an operational data artifact (as opposed to the attendance CSV in [Jccm](jccm.md)). It likely fed into [Viewtilog Overview](../productos/viewtilog-overview.md) pipeline or [Autodiscovery](../configuracion/autodiscovery.md) exercises.
- Security ministry environments require strict [Roles](../configuracion/roles.md) and [Users](../configuracion/users.md) management, [Ldap Integration](../integraciones/ldap-integration.md) or [Active Directory](../integraciones/active-directory.md) integration, and potentially [Mfa Configuration](../integraciones/mfa-configuration.md) — all covered in the [Vc De Agenda](../cursos/vc-de-agenda.md).
- The [Etl Pipeline](../conceptos/etl-pipeline.md) and [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) are relevant for aggregating security operations telemetry at scale.
- This client has two training engagements: this VC-LDA track and a separate [Ministerio Interior](ministerio-interior.md) VC-WDP engagement covering [Viewtimon Overview](../productos/viewtimon-overview.md) and wire data analysis.

## Related Clients

[Ministerio Interior](ministerio-interior.md) covers the same ministry's Wire Data training. Other public sector clients include [Ayto Madrid](ayto-madrid.md), [Jccm](jccm.md), [Junta Andalucia](junta-andalucia.md). The dual-track engagement (VC-LDA + VC-WDP) makes the Ministerio del Interior unique in the training corpus.
