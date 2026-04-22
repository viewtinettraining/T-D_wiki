---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Viewtinet Documentation Wiki — Master Index'
id: AZ8-VTY-PR7-MXO
slug: index
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---
# Viewtinet Documentation Wiki — Master Index

> **Platform:** Viewtinet v6.3.5 | Network Monitoring & Management  
> **Pages:** 115 | **Last updated:** 2026-04-22

Start here → [Viewtinet Platform Overview](productos/viewtinet-platform-overview.md)

---

## Products (`productos/`)

| Page | Summary |
|------|---------|
| [Viewtinet Platform Overview](productos/viewtinet-platform-overview.md) | Full platform overview: product suite, architecture, use cases |
| [Viewtimanager Overview](productos/viewtimanager-overview.md) | ViewtiManager — main control center and management GUI |
| [Viewtilog Overview](productos/viewtilog-overview.md) | ViewtiLog — log collection, indexing, and storage engine |
| [Viewtimon Overview](productos/viewtimon-overview.md) | ViewtiMon — Deep Packet Inspection real-time traffic analyzer |
| [Viewtisight Overview](productos/viewtisight-overview.md) | ViewtiSight — analytics, dashboards, and BI layer |
| [Viewtisight Features](productos/viewtisight-features.md) | ViewtiSight features: Dashboard Composer, Metrics Composer, QueryBuilder, PDF Reporter |
| [Viewtiqos Overview](productos/viewtiqos-overview.md) | ViewtiQoS — traffic shaping and QoS policy enforcement |
| [Viewtibot Overview](productos/viewtibot-overview.md) | ViewtiBot — AI assistant for Viewtinet (ChatGPT-based) |
| [Vs Data Broker Overview](productos/vs-data-broker-overview.md) | VS Data Broker — ETL pipeline and plugin management |
| [Viewtinet Appliance](productos/viewtinet-appliance.md) | Hardware appliance: layout, racking, IPMI, IP management |
| [Rest Api](productos/rest-api.md) | ViewtiSight REST API: authentication, endpoints, query format |

---

## Installation (`instalacion/`)

| Page | Summary |
|------|---------|
| [Os Setup](instalacion/os-setup.md) | Ubuntu Server OS setup: mandatory `viewtinet` user, profile |
| [Hdd Partitioning](instalacion/hdd-partitioning.md) | RAID disk groups and partition scheme (OS: RAID1/XFS; Data: RAID10/ext4) |
| [System Configuration](instalacion/system-configuration.md) | Post-install SSH and NTP configuration |
| [Server Info](instalacion/server-info.md) | Retrieving server-info.txt for licensing |
| [Installation Bundle](instalacion/installation-bundle.md) | Bundle download, SCP upload, and extraction |
| [Installation Bundle Steps](instalacion/installation-bundle-steps.md) | Three-step installation: `deploy.sh`, `install.sh` × 2 |
| [Upload License](instalacion/upload-license.md) | .key license file upload via ViewtiManager GUI (port 4200) |
| [User Admin Activation](instalacion/user-admin-activation.md) | First-login admin activation (default: `admin / Viewtinet01!`) |
| [Viewtilog Installation](instalacion/viewtilog-installation.md) | ViewtiLog standalone and HA cluster installation |
| [Viewtimon Installation](instalacion/viewtimon-installation.md) | ViewtiMon installation, NIC assignment, kernel fine-tuning |
| [Viewtiqos Installation](instalacion/viewtiqos-installation.md) | ViewtiQoS installation and NIC binding sequence |
| [Viewtisight Installation](instalacion/viewtisight-installation.md) | ViewtiSight cluster installation and port table |
| [Ubuntu Upgrade](instalacion/ubuntu-upgrade.md) | Ubuntu 20.04 → 24.04 two-stage upgrade procedure |

---

## Configuration (`configuracion/`)

| Page | Summary |
|------|---------|
| [Login](configuracion/login.md) | ViewtiManager login: URL, default credentials, first access |
| [Gui Overview](configuracion/gui-overview.md) | GUI layout, navigation, module sections |
| [License Management](configuracion/license-management.md) | License upload, enforcement, limits |
| [Users](configuracion/users.md) | User creation, management, password policies |
| [Roles](configuracion/roles.md) | Role-based access control, predefined roles |
| [Groups](configuracion/groups.md) | User groups and group-based permissions |
| [Tenants](configuracion/tenants.md) | Multi-tenancy: tenant management and isolation |
| [System Updates](configuracion/system-updates.md) | Platform update procedure via GUI |
| [Inventory Management](configuracion/inventory-management.md) | Device inventory overview and management |
| [Autodiscovery](configuracion/autodiscovery.md) | Automatic device discovery configuration |
| [Manual Provisioning](configuracion/manual-provisioning.md) | Manual device provisioning steps |
| [Csv Provisioning](configuracion/csv-provisioning.md) | Bulk device provisioning via CSV file |
| [Inventory Maintenance](configuracion/inventory-maintenance.md) | Inventory maintenance tasks |
| [Configuration Manager](configuracion/configuration-manager.md) | Configuration Manager module overview |
| [Configuration Commands](configuracion/configuration-commands.md) | Commands available in Configuration Manager |
| [Configuration Tasks](configuracion/configuration-tasks.md) | Automated tasks in Configuration Manager |

---

## Integrations (`integraciones/`)

### Authentication
| Page | Summary |
|------|---------|
| [Viewtiauth](integraciones/viewtiauth.md) | ViewtiAuth: authentication orchestration, fallback flow |
| [Active Directory](integraciones/active-directory.md) | Active Directory integration: setup, prerequisites, configuration |
| [Ad Groups Roles](integraciones/ad-groups-roles.md) | Mapping AD groups to Viewtinet roles |
| [Ldap Integration](integraciones/ldap-integration.md) | LDAP integration: prerequisites and configuration |
| [Mfa Configuration](integraciones/mfa-configuration.md) | Multi-factor authentication (SMTP + email OTP) |

### Data Sources & Extractors
| Page | Summary |
|------|---------|
| [Data Sources Overview](integraciones/data-sources-overview.md) | All supported data source types organized by category |
| [Snmp Extractor](integraciones/snmp-extractor.md) | SNMP polling extractor |
| [Snmp Trap Connector](integraciones/snmp-trap-connector.md) | SNMP Trap listener extractor |
| [Netflow Extractor](integraciones/netflow-extractor.md) | NetFlow v5/v9/IPFIX data extraction |
| [Sflow Extractor](integraciones/sflow-extractor.md) | sFlow data extraction |
| [Syslog Extractor](integraciones/syslog-extractor.md) | Syslog (UDP/TCP) data extraction |
| [Ssh Extractor](integraciones/ssh-extractor.md) | SSH-based remote command data extraction |
| [Wmi Extractor](integraciones/wmi-extractor.md) | WMI Windows data extraction |
| [Windows Remote Management](integraciones/windows-remote-management.md) | Windows Remote Management (WRM) extractor |
| [Csv Extractor](integraciones/csv-extractor.md) | CSV file data extraction |
| [Mongodb Extractor](integraciones/mongodb-extractor.md) | MongoDB query-based data extraction |
| [Icmp Extractor](integraciones/icmp-extractor.md) | ICMP ping/reachability monitoring |
| [Python Task Extractor](integraciones/python-task-extractor.md) | Custom Python script extractor |
| [Ethernet Streamer](integraciones/ethernet-streamer.md) | Continuous binary traffic listener (Syslog/NetFlow/sFlow) |
| [Flow Emitter](integraciones/flow-emitter.md) | Internal ViewtiMon DPI connector |
| [File List Extractor](integraciones/file-list-extractor.md) | Scheduled directory monitor for file collection |
| [Command Executor](integraciones/command-executor.md) | Shell command/script extractor |

### Transform & Load
| Page | Summary |
|------|---------|
| [Column Constant Adder](integraciones/column-constant-adder.md) | Transform: add a constant to numeric or string columns |
| [Data Producers](integraciones/data-producers.md) | Load phase: 7 producer types (DB, Kafka, CSV, Syslog, SCP…) |

---

## Concepts (`conceptos/`)

| Page | Summary |
|------|---------|
| [Viewtinet Platform Overview](productos/viewtinet-platform-overview.md) | Platform architecture and product relationships |
| [Ubuntu Compatibility](conceptos/ubuntu-compatibility.md) | Supported OS: Ubuntu 20.04 LTS and 24.04 LTS |
| [Standalone Vs Cluster](conceptos/standalone-vs-cluster.md) | Standalone vs HA cluster deployment modes |
| [Ha Architecture](conceptos/ha-architecture.md) | HA: Keepalived/VIP, HAProxy, active-passive failover |
| [Ipmi Management](conceptos/ipmi-management.md) | IPMI configuration, web UI, remote console |
| [Plugin Architecture](conceptos/plugin-architecture.md) | Plugin system: templates vs customized plugins |
| [Plugin Template](conceptos/plugin-template.md) | Plugin template: base structure and purpose |
| [Customized Plugin](conceptos/customized-plugin.md) | Customized plugin: creation and configuration |
| [Plugin Schema](conceptos/plugin-schema.md) | Plugin data schema definition |
| [Plugin Categories](conceptos/plugin-categories.md) | Plugin category classification system |
| [Etl Pipeline](conceptos/etl-pipeline.md) | Extract-Transform-Load pipeline in VS Data Broker |
| [Alarms System](conceptos/alarms-system.md) | Alarms: types, severity levels, configuration, notifications |
| [Data Sources Integration](conceptos/data-sources-integration.md) | Data source integration: protocols, methods, pipeline |
| [Cli Reference](conceptos/cli-reference.md) | CLI tool: directory structure, container management, key scripts |

---

## Training Programs (`formacion/`)

| Page | Summary |
|------|---------|
| [Training Overview](formacion/training-overview.md) | Viewtinet Training & Certification department: mission, delivery formats, beginner-to-expert pathway |
| [Certification Paths](formacion/certification-paths.md) | Five certification verticals; VCOA as mandatory core; progression flow |
| [Vsp](formacion/vsp.md) | VSP — Viewtinet Sales Professional (1h, online, sales positioning) |
| [Vc Psp](formacion/vc-psp.md) | VC-PSP — Certified Presales Solutions Professional (8h, full agenda, case studies) |
| [Vc Oa](formacion/vc-oa.md) | VC-OA / VCOA — Certified Observability Analyst (16h, 6 modules, mandatory analytical core) |
| [Vc De](formacion/vc-de.md) | VC-DE — Certified Data Engineer (16h, requires VC-OA, Viewtilog/Smart Data Broker, formerly VC-LDA) |
| [Vc Wde](formacion/vc-wde.md) | VC-WDE / VC-WDP — Wire Data Engineer (8h, ViewtiMon + ViewtifyQoS, DPI) |

---

## Course Content (`cursos/`)

| Page | Summary |
|------|---------|
| [Vcoa Modules](cursos/vcoa-modules.md) | VCOA 6-module breakdown: theory vs lab, GUI/Metrics/Dashboards/Alarms |
| [Vc De Agenda](cursos/vc-de-agenda.md) | VC-DE full agenda: Viewtimanager deep dive + Viewtilog/Smart Data Broker |
| [Vc Wde Agenda](cursos/vc-wde-agenda.md) | VC-WDE agenda: hardware, Sniffer/Inline deployment, ViewtiMon, ViewtifyQoS lab |

---

## Customer Training Projects (`clientes/`)

| Page | Track | Sector |
|------|-------|--------|
| [Giss](clientes/giss.md) | VC-LDA | Technology — most complete set: 7 PDFs + 7 PPTs + workbook |
| [Junta Andalucia](clientes/junta-andalucia.md) | VC-LDA | Public — 11 PDFs (theory + practice); via Telefónica |
| [Mapfre Usa](clientes/mapfre-usa.md) | VC-LDA | Insurance — 9-module PPT set, US client |
| [Ayto Madrid](clientes/ayto-madrid.md) | VC-LDA | Public — Ayuntamiento de Madrid, 5-module set |
| [Cepsa](clientes/cepsa.md) | VC-LDA | Energy — 4-module compact set |
| [Md](clientes/md.md) | VC-LDA | IT — 7 PPTs, includes Hardware module |
| [Jccm](clientes/jccm.md) | VC-LDA | Public — Castilla-La Mancha, includes attendance CSV |
| [Mininterior Lda](clientes/mininterior-lda.md) | VC-LDA | Government — includes Linux inventory CSV |
| [Claro Peru](clientes/claro-peru.md) | VC-LDA | Telecom — only Latin American client |
| [Consum](clientes/consum.md) | VC-LDA | Retail/Cooperative |
| [Rem Expal](clientes/rem-expal.md) | VC-LDA | Defense/Explosives |
| [Ministerio Interior](clientes/ministerio-interior.md) | VC-WDP | Government — 7 PDFs + 7 PPTs, most complete Wire Data set |
| [Gbo Balear](clientes/gbo-balear.md) | VC-WDP | IT Services — 5-module standard Wire Data set |

---

## Sources (`fuentes/`)

| Page | Summary |
|------|---------|
| [Installation Guide Hub](fuentes/installation-guide-hub.md) | documentation_hub/installation-guide/ — 25 source files |
| [Viewtimanager User Guide](fuentes/viewtimanager-user-guide.md) | documentation_hub/viewtimanager-user-guide/ — core sections |
| [Vs Data Broker Section](fuentes/vs-data-broker-section.md) | documentation_hub/v-dot-s-data-broker/ — 31 source files |
| [Viewtibot Section](fuentes/viewtibot-section.md) | documentation_hub/viewtibot/about.md |
| [Ubuntu Upgrade Guide](fuentes/ubuntu-upgrade-guide.md) | documentation_hub/upgrade-to-ubuntu-24-dot-04/ — 3 source files |
| [Cli Guide Pdf](fuentes/cli-guide-pdf.md) | PDFs_Guides/CLI/viewtinet-cli-guide_en_v6.3.5_v1.0.pdf |
| [Alarms Guide Pdf](fuentes/alarms-guide-pdf.md) | PDFs_Guides/Viewtimanager/alarms-user-guide_en_v6.3_1.0.pdf |
| [Data Sources Guide Pdf](fuentes/data-sources-guide-pdf.md) | PDFs_Guides/Viewtimanager/data-sources-integration-guide_en_v6.3.pdf |
| [Ad Integration Pdf](fuentes/ad-integration-pdf.md) | PDFs_Guides/Viewtimanager/active-directory-integration-guide_en_v6.3.pdf |
| [Rest Api Pdf](fuentes/rest-api-pdf.md) | Product Features/Viewtinet_Viewtisight_REST_API_Specification-v1.5.pdf |
| [Viewtisight Guide Pdf](fuentes/viewtisight-guide-pdf.md) | PDFs_Guides/Viewtisight/viewtisight-user-guide_en_v6.3.pdf |
| [Solution Description Pdf](fuentes/solution-description-pdf.md) | Product Features/Viewtinet Solution Description 052019v2.pdf |
| [Viewtinet Indicators Pdf](fuentes/viewtinet-indicators-pdf.md) | Product Features/Viewtinet Indicators.pdf |
| [Portfolio Training 2026](fuentes/portfolio-training-2026.md) | Portfolio/6.3.5/Viewtinet_Training_Portfolio_v2026_1.4.pdf — all courses 2026 |
| [Cursos Projects Corpus](fuentes/cursos-projects-corpus.md) | Cursos/Projects/ — all customer training project files |
