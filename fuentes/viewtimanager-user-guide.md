---
tags: [fuentes, viewtimanager]
tipo: fuente
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ViewtiManager User Guide — Source Index

This page is the hub for the ViewtiManager User Guide source documentation. It links every raw source file to its corresponding wiki page. The guide covers the full [[viewtimanager-overview|ViewtiManager]] platform, from initial login to advanced configuration automation.

## Core Sections

| Topic | Wiki Page | Source File |
|---|---|---|
| Introduction | [[viewtimanager-overview]] | about-viewtimanager-user-guide.md |
| GUI Overview | [[gui-overview]] | gui-overview.md |
| Login / Access | [[login]] | login.md |
| License Management | [[license-management]] | license.md |

## Admin Section

| Topic | Wiki Page | Source File |
|---|---|---|
| Users | [[users]] | admin/users.md |
| Roles | [[roles]] | admin/roles.md |
| Groups | [[groups]] | admin/groups.md |
| Tenants | [[tenants]] | admin/tenants.md |
| System Updates | [[system-updates]] | admin/updates.md |
| ViewtiAuth Integrations | [[viewtiauth]] | admin/auth/viewtiauth-integrations.md |
| MFA Configuration | [[mfa-configuration]] | admin/auth/mfa-configuration.md |

## Active Directory Integration

| Topic | Wiki Page | Source File |
|---|---|---|
| AD Integration Intro | [[active-directory]] | admin/auth/active-directory-integration/intro-ad-integration.md |
| AD Prerequisites | [[active-directory]] | admin/auth/active-directory-integration/prerequisites.md |
| AD Integration Steps | [[active-directory]] | admin/auth/active-directory-integration/ad-integration.md |
| AD Groups & Roles | [[ad-groups-roles]] | admin/auth/active-directory-integration/groups-and-roles.md |
| GUI Login for AD Users | [[ad-groups-roles]] | admin/auth/active-directory-integration/gui-logging-for-ad-users.md |

## LDAP Integration

| Topic | Wiki Page | Source File |
|---|---|---|
| LDAP Prerequisites | [[ldap-integration]] | admin/auth/ldap-integration/prerequisites.md |
| LDAP Integration Steps | [[ldap-integration]] | admin/auth/ldap-integration/ldap-integration.md |

## Inventory Section

| Topic | Wiki Page | Source File |
|---|---|---|
| Inventory About | [[inventory-management]] | inventory/about.md |
| Autodiscovery | [[autodiscovery]] | inventory/autodiscovery.md |
| Manual Provisioning | [[manual-provisioning]] | inventory/manual-provisioning.md |
| Provisioning via CSV | [[csv-provisioning]] | inventory/provisioning-via-csv.md |
| Inventory Maintenance | [[inventory-maintenance]] | inventory/inventory-maintenance.md |

## Configuration Manager Section

| Topic | Wiki Page | Source File |
|---|---|---|
| Configuration Manager Intro | [[configuration-manager]] | configuration-manager/intro.md |
| Configuration Manager Prerequisites | [[configuration-manager]] | configuration-manager/prerequisites.md |
| Configurations | [[configuration-manager]] | configuration-manager/configurations.md |
| Commands | [[configuration-commands]] | configuration-manager/commands.md |
| Tasks | [[configuration-tasks]] | configuration-manager/tasks.md |

## Related Pages

The ViewtiManager guide builds on the installation work documented in [[installation-bundle-steps]], assumes a working [[upload-license|license]], and integrates with products like [[viewtisight-overview]], [[viewtilog-overview]], [[viewtimon-overview]], and [[viewtiqos-overview]]. The [[vs-data-broker-overview]] and [[plugin-architecture]] are referenced throughout the inventory and monitoring sections.
