---
tags: [configuracion, viewtimanager, autenticacion]
tipo: tecnica
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Login

Access to the Viewtinet platform is handled through the [[viewtiauth|Viewtiauth]] module, which provides centralized authentication for all components. Users must authenticate before being allowed to access [[viewtimanager-overview|ViewtiManager]], [[viewtisight-overview|ViewtiSight]], or other system modules.

## Access URLs

Viewtiauth listens on two ports:

| Protocol | URL Format | Notes |
|---|---|---|
| HTTP | `http://<platform-ip>:4200` | Insecure — not recommended for production |
| HTTPS | `https://<platform-ip>:4201` | Secure — recommended |

Always use HTTPS in production environments. The platform may display a browser warning if self-signed certificates are in use. Contact Viewtinet Helpdesk to install trusted certificates.

## Login Form

Once connected to the login URL, the form requires:

- **Username**
- **Password**
- **Language selection** (bottom dropdown)

Click **Login** to submit credentials for validation by Viewtiauth.

## Authentication Flow

1. Credentials are validated by the [[viewtiauth|Viewtiauth]] module.
2. On success, the user is redirected to the **App Selector** screen.
3. The App Selector shows all modules the user has permission to access based on their assigned [[roles|role]].

Available modules in the App Selector:
- **ViewtiSight** — visualization and dashboards
- **ViewtiManager** — system and module administration

## Direct Module Access

Modules can also be accessed directly via their dedicated ports:

| Module | HTTP | HTTPS |
|---|---|---|
| ViewtiManager | `http://<platform-ip>:5000` | `https://<platform-ip>:5001` |

When accessing these ports without an existing browser session, the user is automatically redirected to the Viewtiauth login page before being granted access. This allows bookmarking module URLs while preserving centralized session management.

## Default Credentials

After initial installation, the default admin credentials are activated during the [[user-admin-activation|admin user activation]] step. Passwords must comply with the [[users|password policy]] (12+ characters, digit, uppercase, special character).

## Related Pages

- [[viewtiauth]] — Authentication backends and integration options
- [[mfa-configuration]] — Enable two-factor authentication
- [[active-directory]] — AD-based login for domain users
- [[ldap-integration]] — LDAP-based authentication setup
