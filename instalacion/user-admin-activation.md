---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'User Admin Activation'
id: 8RO-3RW-14D-4YH
slug: user-admin-activation
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# User Admin Activation

Once the [three-step bundle installation](installation-bundle-steps.md) is complete, the admin user must be activated before the platform can be used. This is a one-time procedure that sets the permanent admin password.

## Default Credentials

The platform ships with the following initial credentials:

| Field | Value |
|---|---|
| Username | `admin` |
| Password | `Viewtinet01!` |

These default credentials are used only for the first login and must be changed during activation.

## Activation Procedure

1. Open a web browser and navigate to `http://<SERVER_IP>:4200`
   - Replace `<SERVER_IP>` with the IP address of the appliance, VM, or COTS server
2. At the login screen, enter the default credentials: username `admin`, password `Viewtinet01!`
3. You will be immediately prompted to create a new password
4. Enter your desired password and confirm it
5. Store this password securely — it will be the admin account password going forward

## After Activation

Once the admin password is set:

- Proceed to [Server Info](server-info.md) to download the server-info.txt for licensing
- Then [Upload License](upload-license.md) to activate platform features via [ViewtiManager](../productos/viewtimanager-overview.md)
- Configure additional [user accounts](../configuracion/users.md) and [user roles](../configuracion/roles.md) as needed

## Notes on Cluster Deployments

For [cluster deployments](../conceptos/standalone-vs-cluster.md), admin activation and license upload must be performed on each node independently. Refer to [Viewtisight Installation](viewtisight-installation.md) and [Viewtilog Installation](viewtilog-installation.md) for cluster-specific steps.

The admin user is the primary account for accessing [the GUI](../configuracion/gui-overview.md) and managing modules. For organizational setups, review [Active Directory](../integraciones/active-directory.md) or [LDAP integration](../integraciones/ldap-integration.md) for centralized authentication.

See [Installation Guide Hub](../fuentes/installation-guide-hub.md) for the full source index.
