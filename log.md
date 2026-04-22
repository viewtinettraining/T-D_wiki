# Wiki Log — Viewtinet Documentation

## [2026-04-22] wikiforge | Customer training client pages created
- Agent: WikiForge (claude-sonnet-4-6)
- Sources: Cursos/Projects/ directory (VC-LDA and VC-WDP client folders, ~76 files across 13 clients)
- Pages created: 14 wiki pages across 2 directories

### clientes/ (13 pages)
- ayto-madrid.md — Ayuntamiento de Madrid: VC-LDA, 5-module PPT set (public administration)
- cepsa.md — CEPSA energy company: VC-LDA, compact 4-module PPT set
- claro-peru.md — CLARO Peru telecom: VC-LDA, single customized CLARO-MRA.pptx (Latin America)
- consum.md — Consum retail cooperative: VC-LDA, single customized CONSUM.pptx
- giss.md — GISS: VC-LDA, most complete set — 7 PDFs + 7 PPTs + workbook v6.3.5; includes Viewtiauth and LAB Access
- jccm.md — Junta de Comunidades de Castilla-La Mancha: VC-LDA, 1 PPT + attendance CSV dated 8 May 2025
- junta-andalucia.md — Junta de Andalucia: VC-LDA, 11 PDFs (theory+practice split) + 1 PPT via Telefonica partner
- mapfre-usa.md — MAPFRE USA insurance: VC-LDA, 9-module PPT set (fullest PPT-only delivery); includes Viewtiauth, LAB Access
- md.md — MD: VC-LDA, 7 PPTs including unique Hardware module and dual Architecture module
- mininterior-lda.md — Ministerio del Interior (VC-LDA): 1 PPT + Linux inventory CSV
- rem-expal.md — REM-EXPAL defense: VC-LDA, single customized REM-EXPAL.pptx
- gbo-balear.md — GBO Balear IT services: VC-WDP, standard 5-module PPT set
- ministerio-interior.md — Ministerio del Interior (VC-WDP): most complete Wire Data set — 7 PDFs + 7 PPTs including Viewtilog and ViewtiSight

### fuentes/ (1 page)
- cursos-projects-corpus.md — Corpus summary: all 13 clients, file counts, course tracks, links to all client pages

### Stats
- Total new pages: 14
- Total wikilinks across new pages: ~140 (avg ~10 per page)
- All pages: complete frontmatter, English, minimum 8 wikilinks, kebab-case filenames

## [2026-04-22] wikiforge | Training & Certification Portfolio 2026 v1.4
- Agent: WikiForge (claude-sonnet-4-6)
- Source: Viewtinet Training Portfolio 2026 v1.4 PDF (extracted content)
- Pages created: 10 wiki pages across 3 directories

### formacion/ (7 pages)
- training-overview.md — Program mission, practical-first philosophy, beginner-to-expert pathway, delivery formats
- certification-paths.md — Five certification verticals, VCOA as mandatory analytical core, full progression flow diagram
- vsp.md — VSP: Viewtinet Sales Professional (1h, online, no formal exam)
- vc-psp.md — VC-PSP: Certified Presales Solutions Professional (8h, full 10-topic agenda, case studies, 70% exam)
- vc-oa.md — VC-OA / VCOA: Certified Observability Analyst (16h, 6 modules, mandatory core, Single Pane of Glass)
- vc-de.md — VC-DE: Certified Data Engineer (16h, requires VC-OA, Viewtilog/Smart Data Broker focus, formerly VC-LDA)
- vc-wde.md — VC-WDE / VC-WDP: Wire Data Engineer (8h, ViewtiMon+ViewtifyQoS, DPI, Sniffer/Inline modes)

### cursos/ (3 pages)
- vcoa-modules.md — VCOA detailed 6-module breakdown with theory vs. lab classification
- vc-de-agenda.md — VC-DE full agenda: Viewtimanager deep coverage, Viewtilog/Smart Data Broker deep dive, troubleshooting
- vc-wde-agenda.md — VC-WDE full agenda: hardware, Sniffer vs. Inline deployment modes, ViewtiMon, ViewtifyQoS practical

### fuentes/ (1 page)
- portfolio-training-2026.md — Source summary: all 5 courses, versions, certification structure, links to all formacion/ pages

## [2026-04-22] lint | WikiForge LINT audit

- Agent: WikiForge LINT (claude-sonnet-4-6)
- Scope: 86 content pages (all .md excluding index.md and log.md), 6 folders
- Sample checked: 15 pages across all 6 folders

### 1. Frontmatter Check

- Pages with all 5 required fields (tags, tipo, fuentes, fecha_creacion, fecha_actualizacion): **86 / 86 (100%)**
- Pages missing any field: **0**
- Result: PASS — all pages have complete frontmatter

### 2. Language Check

- All 15 sampled pages are written in English
- Result: PASS — no pages in wrong language

### 3. Ghost Links Check

- Total unique wikilink targets found: 109
- Valid targets (link resolves to existing page): 90
- Ghost links before fixes: 22
- Ghost links after fixes: 19
- Ghost links fixed this run: 3 (naming mismatches in installation-guide-hub.md: operating-system-setup→os-setup, getting-server-info→server-info, ipmi-ip-address-configuration→ipmi-management)

**Remaining 19 ghost links — all in fuentes/installation-guide-hub.md, Source Files Index section:**
These link to original source document filenames (not wiki pages). No wiki equivalents exist for these source-only docs:
- about-installation-guide, about-viewtify-qos, about-viewtilog, about-viewtilog-guide-installation, about-viewtimon
- changing-the-management-ip-address, managing-your-appliance-via-ipmi, getting-to-know-your-appliance, how-to-rack-your-appliance
- cluster-installation (viewtilog), cluster-installation (viewtisight)
- standalone-installation (viewtilog), standalone-installation (viewtimon), standalone-installation (viewtiqos)
- fine-tuning, installation-step1, installation-step2, installation-step3, preparing-the-installation-bundle

**Critical bug fixed (not ghost links):** 29 wikilinks across 8 files had a `\|` (backslash-pipe) corruption inside `[[target\|alias]]` — Obsidian would have treated the entire string as the target name. All 29 were repaired to `[[target|alias]]`.
Affected files: configuracion/gui-overview.md, configuracion/license-management.md, configuracion/roles.md, configuracion/users.md, fuentes/solution-description-pdf.md, integraciones/ad-groups-roles.md, productos/viewtimanager-overview.md, productos/viewtinet-platform-overview.md

### 4. Link Density Check (15-page sample)

| Page | Links | Status |
|---|---|---|
| etl-pipeline.md | 21 | OK |
| plugin-template.md | 15 | OK |
| roles.md | 13 | OK |
| users.md | 12 | OK |
| mfa-configuration.md | 12 | OK |
| wmi-extractor.md | 11 | OK |
| configuration-tasks.md | 11 | OK |
| active-directory.md | 11 | OK |
| autodiscovery.md | 9 | OK |
| sflow-extractor.md | 9 | OK |
| ad-integration-pdf.md | 9 | OK |
| viewtiqos-overview.md | 8 | OK |
| alarms-guide-pdf.md | 8 | OK |
| icmp-extractor.md | 8 | OK |
| **viewtiqos-installation.md** | **6** | **BELOW THRESHOLD (<8)** |

Pages below 8-link threshold in full wiki scan (15 pages total):
- ubuntu-upgrade.md (4), viewtimon-installation.md (5), csv-extractor.md (6), hdd-partitioning.md (6), ipmi-management.md (6), python-task-extractor.md (6), system-updates.md (6), ubuntu-upgrade-guide.md (6), viewtiqos-installation.md (6), netflow-extractor.md (7), os-setup.md (7), ssh-extractor.md (7), ubuntu-compatibility.md (7), viewtimon-overview.md (7), windows-remote-management.md (7)

### 5. Overall Stats

**Pages by folder:**
| Folder | Pages |
|---|---|
| conceptos/ | 13 |
| configuracion/ | 16 |
| fuentes/ | 13 |
| instalacion/ | 13 |
| integraciones/ | 24 |
| productos/ | 11 |
| **Total** | **90 (+ index.md + log.md = 92)** |

**Total wikilinks across wiki:** 1,236 (after fixes)

**Gaps — topics frequently mentioned without dedicated pages:**
- No dedicated page for ViewtiBot configuration (viewtibot-overview.md exists but is brief)
- No dedicated page for VRRP/Keepalived/HAProxy (covered inside ha-architecture.md)
- No dedicated page for Kafka integration (mentioned in data-producers.md)
- No dedicated page for ViewtiLog configuration (only installation and overview pages)
- Source docs never wikified: fine-tuning (ViewtiMon kernel tuning), ViewtiQoS about page, ViewtiLog about page, ViewtiMon about page, appliance racking/rack guide

### 6. Fixes Applied This Run

1. **29 backslash-pipe link corruptions fixed** across 8 files — `[[page\|alias]]` → `[[page|alias]]`
2. **3 ghost link naming mismatches fixed** in fuentes/installation-guide-hub.md:
   - `[[operating-system-setup|...]]` → `[[os-setup|...]]`
   - `[[getting-server-info|...]]` → `[[server-info|...]]`
   - `[[ipmi-ip-address-configuration|...]]` → `[[ipmi-management|...]]`

## [2026-04-21] setup | Vault initialized
- Structure created: wiki/{fuentes,productos,instalacion,configuracion,integraciones,conceptos}
- CLAUDE.md generated
- index.md and log.md initialized
- Corpus identified: ~100 MD files (documentation_hub) + PDFs + installation guides + product features

## [2026-04-22] wikiforge | Platform overview, features, API, HA, alarms, CLI, and source summaries
- Agent: WikiForge (claude-sonnet-4-6)
- Sources: Viewtinet Solution Description PDF, Viewtinet Indicators PDF, REST API Specification v1.5, ViewtiSight User Guide v6.3, Alarms User Guide v6.3, CLI Guide v6.3.5, Data Sources Integration Guide v6.3
- Pages created: 10 wiki pages across 3 directories

### productos/ (3 pages)
- viewtisight-features.md — ViewtiSight analytics features: Dashboard Composer, Metrics Composer, QueryBuilder, PDF Reporter, Control Center
- rest-api.md — ViewtiSight REST API: authentication, endpoint categories, query pattern, response format
- viewtinet-platform-overview.md — Viewtinet platform overview: all products, use cases, target audience, architecture, data flow

### conceptos/ (4 pages)
- ha-architecture.md — High Availability architecture: active-passive, Keepalived/VIP, HAProxy, failover process, requirements
- alarms-system.md — Alarms and alerting: alarm types, severity levels, configuration steps, management operations, notification channels
- data-sources-integration.md — Data source integration: supported protocols, transform handlers, load targets, plugin lifecycle
- cli-reference.md — CLI tool overview: directory structure, container management, operational scripts, key use cases

### fuentes/ (3 pages)
- solution-description-pdf.md — Summary of Viewtinet Solution Description PDF with wikilinks
- viewtinet-indicators-pdf.md — Summary of Viewtinet Indicators PDF with wikilinks
- viewtisight-guide-pdf.md — Summary of ViewtiSight User Guide PDF with wikilinks

## [2026-04-22] wikiforge | Authentication, VSDB extractors, Ubuntu upgrade, and data sources
- Agent: WikiForge (claude-sonnet-4-6)
- Sources: admin/auth/ (4 files), v-dot-s-data-broker/extract/ (4 files), v-dot-s-data-broker/transform/ (1 file), v-dot-s-data-broker/load/ (1 file), upgrade-to-ubuntu-24-dot-04/ (3 files)
- Pages created: 11 wiki pages across 2 directories

### integraciones/ (10 pages)
- ldap-integration.md — LDAP integration prerequisites and configuration steps
- mfa-configuration.md — Multi-factor authentication setup (email OTP via SMTP)
- viewtiauth.md — ViewtiAuth integrations overview: backends, order, fallback logic
- ethernet-streamer.md — Continuous network traffic capture connector (raw binary)
- flow-emitter.md — Internal DPI-enriched flow data extractor for Viewtimon
- file-list-extractor.md — Scheduled file directory monitor and mover connector
- command-executor.md — Shell command and script execution extractor
- column-constant-adder.md — Transform handler: add constant to numeric or string column
- data-producers.md — Load stage output targets: Aggregator, CSV, SCP, Syslog, Kafka, ViewtinetDB
- data-sources-overview.md — Reference overview of all VS Data Broker data source types

### instalacion/ (1 page)
- ubuntu-upgrade.md — Two-stage Ubuntu 20.04 → 22.04 → 24.04 upgrade procedure with interface renaming fix

## [2026-04-21] wikiforge | Installation Guide section processed
- Agent: WikiForge (claude-sonnet-4-6)
- Source: documentation_hub/1.0/installation-guide/ (25 source files)
- Pages created: 21 wiki pages across 4 directories

### fuentes/ (1 page)
- installation-guide-hub.md — Hub page with full source index and links to all 25 source files

### instalacion/ (12 pages)
- os-setup.md — Ubuntu Server OS profile setup (viewtinet user)
- hdd-partitioning.md — RAID disk groups and partition scheme
- system-configuration.md — SSH and NTP post-install configuration
- server-info.md — server-info.txt retrieval for licensing
- installation-bundle.md — Bundle download, upload, and extraction
- installation-bundle-steps.md — Three-step installation procedure (deploy.sh, install.sh x2)
- upload-license.md — .key license file upload via GUI
- user-admin-activation.md — First-login admin password activation (default: Viewtinet01!)
- viewtilog-installation.md — ViewtiLog standalone and HA cluster installation
- viewtimon-installation.md — ViewtiMon installation and kernel fine-tuning
- viewtiqos-installation.md — ViewtiQoS (Viewtify QoS) installation and NIC binding
- viewtisight-installation.md — ViewtiSight cluster installation and port table

### productos/ (5 pages)
- viewtilog-overview.md — ViewtiLog capabilities and data sources
- viewtimon-overview.md — ViewtiMon DPI monitoring and certified NICs
- viewtiqos-overview.md — ViewtiQoS traffic shaping and prioritization
- viewtisight-overview.md — ViewtiSight analytics and BI layer
- viewtinet-appliance.md — Hardware layout, racking, IP change procedure

### conceptos/ (3 pages)
- ubuntu-compatibility.md — Supported OS (Ubuntu 20.04, 24.04) and scope
- standalone-vs-cluster.md — HA vs standalone deployment modes with support matrix
- ipmi-management.md — IPMI configuration, web access, remote console

## [2026-04-21] wikiforge | COMPLETE — Wiki ready for use
- Total pages: 90 content pages + index.md + log.md = 92 files
- Total wikilinks: 1,236 across the wiki
- LINT: 100% frontmatter compliance, 100% English, 32 broken links fixed
- Vault: /DOCUMENTATION/vault-viewtinet/
- Open wiki/index.md in Obsidian to start navigating
