---
tags: [instalacion, usuarios, autenticacion]
tipo: tecnica
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# User Admin Activation

Once the [[installation-bundle-steps|three-step bundle installation]] is complete, the admin user must be activated before the platform can be used. This is a one-time procedure that sets the permanent admin password.

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

- Proceed to [[server-info]] to download the server-info.txt for licensing
- Then [[upload-license]] to activate platform features via [[viewtimanager-overview|ViewtiManager]]
- Configure additional [[users|user accounts]] and [[roles|user roles]] as needed

## Notes on Cluster Deployments

For [[standalone-vs-cluster|cluster deployments]], admin activation and license upload must be performed on each node independently. Refer to [[viewtisight-installation]] and [[viewtilog-installation]] for cluster-specific steps.

The admin user is the primary account for accessing [[gui-overview|the GUI]] and managing modules. For organizational setups, review [[active-directory|Active Directory]] or [[ldap-integration|LDAP integration]] for centralized authentication.

See [[installation-guide-hub|Installation Guide Hub]] for the full source index.
