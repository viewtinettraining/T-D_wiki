# Viewtinet Documentation Wiki — Master Index

> **Platform:** Viewtinet v6.3.5 | Network Monitoring & Management  
> **Pages:** 115 | **Last updated:** 2026-04-22

Start here → [[viewtinet-platform-overview|Viewtinet Platform Overview]]

---

## Products (`productos/`)

| Page | Summary |
|------|---------|
| [[viewtinet-platform-overview]] | Full platform overview: product suite, architecture, use cases |
| [[viewtimanager-overview]] | ViewtiManager — main control center and management GUI |
| [[viewtilog-overview]] | ViewtiLog — log collection, indexing, and storage engine |
| [[viewtimon-overview]] | ViewtiMon — Deep Packet Inspection real-time traffic analyzer |
| [[viewtisight-overview]] | ViewtiSight — analytics, dashboards, and BI layer |
| [[viewtisight-features]] | ViewtiSight features: Dashboard Composer, Metrics Composer, QueryBuilder, PDF Reporter |
| [[viewtiqos-overview]] | ViewtiQoS — traffic shaping and QoS policy enforcement |
| [[viewtibot-overview]] | ViewtiBot — AI assistant for Viewtinet (ChatGPT-based) |
| [[vs-data-broker-overview]] | VS Data Broker — ETL pipeline and plugin management |
| [[viewtinet-appliance]] | Hardware appliance: layout, racking, IPMI, IP management |
| [[rest-api]] | ViewtiSight REST API: authentication, endpoints, query format |

---

## Installation (`instalacion/`)

| Page | Summary |
|------|---------|
| [[os-setup]] | Ubuntu Server OS setup: mandatory `viewtinet` user, profile |
| [[hdd-partitioning]] | RAID disk groups and partition scheme (OS: RAID1/XFS; Data: RAID10/ext4) |
| [[system-configuration]] | Post-install SSH and NTP configuration |
| [[server-info]] | Retrieving server-info.txt for licensing |
| [[installation-bundle]] | Bundle download, SCP upload, and extraction |
| [[installation-bundle-steps]] | Three-step installation: `deploy.sh`, `install.sh` × 2 |
| [[upload-license]] | .key license file upload via ViewtiManager GUI (port 4200) |
| [[user-admin-activation]] | First-login admin activation (default: `admin / Viewtinet01!`) |
| [[viewtilog-installation]] | ViewtiLog standalone and HA cluster installation |
| [[viewtimon-installation]] | ViewtiMon installation, NIC assignment, kernel fine-tuning |
| [[viewtiqos-installation]] | ViewtiQoS installation and NIC binding sequence |
| [[viewtisight-installation]] | ViewtiSight cluster installation and port table |
| [[ubuntu-upgrade]] | Ubuntu 20.04 → 24.04 two-stage upgrade procedure |

---

## Configuration (`configuracion/`)

| Page | Summary |
|------|---------|
| [[login]] | ViewtiManager login: URL, default credentials, first access |
| [[gui-overview]] | GUI layout, navigation, module sections |
| [[license-management]] | License upload, enforcement, limits |
| [[users]] | User creation, management, password policies |
| [[roles]] | Role-based access control, predefined roles |
| [[groups]] | User groups and group-based permissions |
| [[tenants]] | Multi-tenancy: tenant management and isolation |
| [[system-updates]] | Platform update procedure via GUI |
| [[inventory-management]] | Device inventory overview and management |
| [[autodiscovery]] | Automatic device discovery configuration |
| [[manual-provisioning]] | Manual device provisioning steps |
| [[csv-provisioning]] | Bulk device provisioning via CSV file |
| [[inventory-maintenance]] | Inventory maintenance tasks |
| [[configuration-manager]] | Configuration Manager module overview |
| [[configuration-commands]] | Commands available in Configuration Manager |
| [[configuration-tasks]] | Automated tasks in Configuration Manager |

---

## Integrations (`integraciones/`)

### Authentication
| Page | Summary |
|------|---------|
| [[viewtiauth]] | ViewtiAuth: authentication orchestration, fallback flow |
| [[active-directory]] | Active Directory integration: setup, prerequisites, configuration |
| [[ad-groups-roles]] | Mapping AD groups to Viewtinet roles |
| [[ldap-integration]] | LDAP integration: prerequisites and configuration |
| [[mfa-configuration]] | Multi-factor authentication (SMTP + email OTP) |

### Data Sources & Extractors
| Page | Summary |
|------|---------|
| [[data-sources-overview]] | All supported data source types organized by category |
| [[snmp-extractor]] | SNMP polling extractor |
| [[snmp-trap-connector]] | SNMP Trap listener extractor |
| [[netflow-extractor]] | NetFlow v5/v9/IPFIX data extraction |
| [[sflow-extractor]] | sFlow data extraction |
| [[syslog-extractor]] | Syslog (UDP/TCP) data extraction |
| [[ssh-extractor]] | SSH-based remote command data extraction |
| [[wmi-extractor]] | WMI Windows data extraction |
| [[windows-remote-management]] | Windows Remote Management (WRM) extractor |
| [[csv-extractor]] | CSV file data extraction |
| [[mongodb-extractor]] | MongoDB query-based data extraction |
| [[icmp-extractor]] | ICMP ping/reachability monitoring |
| [[python-task-extractor]] | Custom Python script extractor |
| [[ethernet-streamer]] | Continuous binary traffic listener (Syslog/NetFlow/sFlow) |
| [[flow-emitter]] | Internal ViewtiMon DPI connector |
| [[file-list-extractor]] | Scheduled directory monitor for file collection |
| [[command-executor]] | Shell command/script extractor |

### Transform & Load
| Page | Summary |
|------|---------|
| [[column-constant-adder]] | Transform: add a constant to numeric or string columns |
| [[data-producers]] | Load phase: 7 producer types (DB, Kafka, CSV, Syslog, SCP…) |

---

## Concepts (`conceptos/`)

| Page | Summary |
|------|---------|
| [[viewtinet-platform-overview]] | Platform architecture and product relationships |
| [[ubuntu-compatibility]] | Supported OS: Ubuntu 20.04 LTS and 24.04 LTS |
| [[standalone-vs-cluster]] | Standalone vs HA cluster deployment modes |
| [[ha-architecture]] | HA: Keepalived/VIP, HAProxy, active-passive failover |
| [[ipmi-management]] | IPMI configuration, web UI, remote console |
| [[plugin-architecture]] | Plugin system: templates vs customized plugins |
| [[plugin-template]] | Plugin template: base structure and purpose |
| [[customized-plugin]] | Customized plugin: creation and configuration |
| [[plugin-schema]] | Plugin data schema definition |
| [[plugin-categories]] | Plugin category classification system |
| [[etl-pipeline]] | Extract-Transform-Load pipeline in VS Data Broker |
| [[alarms-system]] | Alarms: types, severity levels, configuration, notifications |
| [[data-sources-integration]] | Data source integration: protocols, methods, pipeline |
| [[cli-reference]] | CLI tool: directory structure, container management, key scripts |

---

## Training Programs (`formacion/`)

| Page | Summary |
|------|---------|
| [[training-overview]] | Viewtinet Training & Certification department: mission, delivery formats, beginner-to-expert pathway |
| [[certification-paths]] | Five certification verticals; VCOA as mandatory core; progression flow |
| [[vsp]] | VSP — Viewtinet Sales Professional (1h, online, sales positioning) |
| [[vc-psp]] | VC-PSP — Certified Presales Solutions Professional (8h, full agenda, case studies) |
| [[vc-oa]] | VC-OA / VCOA — Certified Observability Analyst (16h, 6 modules, mandatory analytical core) |
| [[vc-de]] | VC-DE — Certified Data Engineer (16h, requires VC-OA, Viewtilog/Smart Data Broker, formerly VC-LDA) |
| [[vc-wde]] | VC-WDE / VC-WDP — Wire Data Engineer (8h, ViewtiMon + ViewtifyQoS, DPI) |

---

## Course Content (`cursos/`)

| Page | Summary |
|------|---------|
| [[vcoa-modules]] | VCOA 6-module breakdown: theory vs lab, GUI/Metrics/Dashboards/Alarms |
| [[vc-de-agenda]] | VC-DE full agenda: Viewtimanager deep dive + Viewtilog/Smart Data Broker |
| [[vc-wde-agenda]] | VC-WDE agenda: hardware, Sniffer/Inline deployment, ViewtiMon, ViewtifyQoS lab |

---

## Customer Training Projects (`clientes/`)

| Page | Track | Sector |
|------|-------|--------|
| [[giss]] | VC-LDA | Technology — most complete set: 7 PDFs + 7 PPTs + workbook |
| [[junta-andalucia]] | VC-LDA | Public — 11 PDFs (theory + practice); via Telefónica |
| [[mapfre-usa]] | VC-LDA | Insurance — 9-module PPT set, US client |
| [[ayto-madrid]] | VC-LDA | Public — Ayuntamiento de Madrid, 5-module set |
| [[cepsa]] | VC-LDA | Energy — 4-module compact set |
| [[md]] | VC-LDA | IT — 7 PPTs, includes Hardware module |
| [[jccm]] | VC-LDA | Public — Castilla-La Mancha, includes attendance CSV |
| [[mininterior-lda]] | VC-LDA | Government — includes Linux inventory CSV |
| [[claro-peru]] | VC-LDA | Telecom — only Latin American client |
| [[consum]] | VC-LDA | Retail/Cooperative |
| [[rem-expal]] | VC-LDA | Defense/Explosives |
| [[ministerio-interior]] | VC-WDP | Government — 7 PDFs + 7 PPTs, most complete Wire Data set |
| [[gbo-balear]] | VC-WDP | IT Services — 5-module standard Wire Data set |

---

## Sources (`fuentes/`)

| Page | Summary |
|------|---------|
| [[installation-guide-hub]] | documentation_hub/installation-guide/ — 25 source files |
| [[viewtimanager-user-guide]] | documentation_hub/viewtimanager-user-guide/ — core sections |
| [[vs-data-broker-section]] | documentation_hub/v-dot-s-data-broker/ — 31 source files |
| [[viewtibot-section]] | documentation_hub/viewtibot/about.md |
| [[ubuntu-upgrade-guide]] | documentation_hub/upgrade-to-ubuntu-24-dot-04/ — 3 source files |
| [[cli-guide-pdf]] | PDFs_Guides/CLI/viewtinet-cli-guide_en_v6.3.5_v1.0.pdf |
| [[alarms-guide-pdf]] | PDFs_Guides/Viewtimanager/alarms-user-guide_en_v6.3_1.0.pdf |
| [[data-sources-guide-pdf]] | PDFs_Guides/Viewtimanager/data-sources-integration-guide_en_v6.3.pdf |
| [[ad-integration-pdf]] | PDFs_Guides/Viewtimanager/active-directory-integration-guide_en_v6.3.pdf |
| [[rest-api-pdf]] | Product Features/Viewtinet_Viewtisight_REST_API_Specification-v1.5.pdf |
| [[viewtisight-guide-pdf]] | PDFs_Guides/Viewtisight/viewtisight-user-guide_en_v6.3.pdf |
| [[solution-description-pdf]] | Product Features/Viewtinet Solution Description 052019v2.pdf |
| [[viewtinet-indicators-pdf]] | Product Features/Viewtinet Indicators.pdf |
| [[portfolio-training-2026]] | Portfolio/6.3.5/Viewtinet_Training_Portfolio_v2026_1.4.pdf — all courses 2026 |
| [[cursos-projects-corpus]] | Cursos/Projects/ — all customer training project files |
