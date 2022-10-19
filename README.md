# selfhosted-authentication-table
List of SelfHosted apps, with information about their support for OpenID / SAML / LDAP / Proxy Auth

✔️ - Supported - all functionality works including mobile apps (if any)  
😔 - Supported, but breaks some features, mobile apps, users have to still be added manually or not maintained  
❌ - Unsupported  
❔ - Not known yet, to be added  

Proxy Auth theoretically works on all of them, but it will break functionality, display double logins etc.   
So only those explicitly working great with it will be marked as such. Otherwise it will be unsupported.  

| **Project**                                                                     | **OpenID** | **LDAP** | **Proxy Auth** | **Additional Info**                                                                                                                                                                                                                                                                                                    |
|---------------------------------------------------------------------------------|------------|----------|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [NextCloud](https://nextcloud.com)                                              | ✔️          | ✔️        | ❌              | Install OpenID or LDAP plugin from interface to enable support                                                                                                                                                                                                                                                         |
| [hedgedoc](https://hedgedoc.org)                                                | ✔️          | ✔️        | ❌              |                                                                                                                                                                                                                                                                                                                        |
| [matrix synapse](https://matrix.org/docs/projects/server/synapse)               | ✔️          | ✔️        | ❌              | LDAP Provided by additional module; openid supported natively                                                                                                                                                                                                                                                          |
| [matrix dendrite](https://github.com/matrix-org/dendrite)                       | ❌          | ❌        | ❌              | Some work on SSO in [this PR](https://github.com/matrix-org/dendrite/pull/2492), some work on LDAP [here](https://github.com/matrix-org/dendrite/pull/1877) but abandoned                                                                                                                                              |
| [Home Assistant](https://www.home-assistant.io)                                 | ❌          | 😔        | 😔              | [hass-proxy-auth](https://github.com/BeryJu/hass-auth-header) for proxy auth, but for some people it breaks mobile app, [hacky scripts](https://gist.github.com/rechner/57c123d243b8adb83ccb1dc94c80847f) for LDAP. [More Info](https://www.home-assistant.io/docs/authentication/providers/)                          |
| [Bookstack](https://www.bookstackapp.com/)                                      | ✔️          | ✔️        | ❌              | [documentation](https://www.bookstackapp.com/docs/admin/) -> `Authentication`                                                                                                                                                                                                                                          |
| [Uptime Kuma](https://uptime.kuma.pet)                                          | ❌          | ❌        | ✔️              | `Settings` > `Advanced` > `Disable Auth` to avoid double login                                                                                                                                                                                                                                                         |
| [gokapi](https://github.com/Forceu/Gokapi)                                      | ✔️          | ❌        | ✔️              | [documentation](https://gokapi.readthedocs.io/en/latest/setup.html#authentication)                                                                                                                                                                                                                                     |
| [audiobookshelf](https://www.audiobookshelf.org/)                               | ❌          | ❌        | ❌              | [#998](https://github.com/advplyr/audiobookshelf/issues/998) for SSO, [#185](https://github.com/advplyr/audiobookshelf/issues/185) for LDAP, [#972](https://github.com/advplyr/audiobookshelf/issues/972) for Proxy, nothing seems to be worked on.                                                                    |
| [Apache Guacamole](https://guacamole.apache.org/)                               | ✔️          | ✔️        | ❌              | possible issues with openid accounts not getting created in guacamole automatically                                                                                                                                                                                                                                    |
| [changedetection](https://github.com/dgtlmoon/changedetection.io)               | ❌          | ❌        | ✔️              | No multi-user support, but it doesn't have that with default auth either                                                                                                                                                                                                                                               |
| [vaultwarden](https://github.com/dani-garcia/vaultwarden)                       | ❌          | ✔️        | ❌              | [Invitation-Based LDAP](https://github.com/dani-garcia/vaultwarden/wiki/Syncing-users-from-LDAP), OpenID being worked on in [#2449](https://github.com/dani-garcia/vaultwarden/pull/2449)                                                                                                                              |
| [Paperless-NGX](https://github.com/paperless-ngx/paperless-ngx)                 | ❌          | ❌        | 😔              | Proxy Auth [possible](https://goauthentik.io/integrations/services/paperless-ng) but doesn't autocreate users, [Issue about User Management](https://github.com/paperless-ngx/paperless-ngx/discussions/625), [possible hacky workaround for OpenID?](https://ciphermenial.github.io/posts/adding-oauth-to-paperless/) |
| [GitLab](https://gitlab.com)                                                    | ✔️          | ✔️        | ❌              | [OpenID documentation](https://docs.gitlab.com/ee/administration/auth/oidc.html), [LDAP documentation](https://docs.gitlab.com/ee/administration/auth/ldap/)                                                                                                                                                           |
| [Gitea](https://gitea.io/en-us/)                                                | ✔️          | ✔️        | ❌              |                                                                                                                                                                                                                                                                                                                        |
| [Calibre-Web](https://github.com/janeczku/calibre-web)                          | ❌          | ✔️        | 😔              | [LDAP documentation](https://github.com/janeczku/calibre-web/wiki/LDAP-Login), proxy auth seems to have issues with OPDS feed, OpenID supports only GitHub and Google OAuth, but generic is [being worked on](https://github.com/janeczku/calibre-web/pull/2211)                                                       |
| [Jellyfin](https://jellyfin.org/)                                               | 😔          | ✔️        | ❌              | [LDAP plugin](https://github.com/jellyfin/jellyfin-plugin-ldapauth), [OpenID plugin](https://github.com/9p4/jellyfin-plugin-sso) breaks apps, [might be solved in the future](https://github.com/jellyfin/jellyfin-meta/issues/28)                                                                                     |
| [docker-mailserver](https://docker-mailserver.github.io/docker-mailserver/edge) | ❌          | 😔        | ❌              | LDAP supported, but unmaintained. OpenID [being worked on](https://github.com/docker-mailserver/docker-mailserver/issues/2713), but I wouldn't count on that as mail client support for xoauth2 is not good                                                                                                            |
| [mailcow](https://mailcow.email/)                                               | ❌          | 😔        | ❌              | [hacky ldapsync script](https://github.com/Programmierus/ldap-mailcow), [issue about auth](https://github.com/mailcow/mailcow-dockerized/issues/2316)                                                                                                                                                                  |
| [mailu](https://mailu.io)                                                       | ❌          | ❌        | ❌              |                                                                                                                                                                                                                                                                                                                        |
| [blink](https://github.com/JaneJeon/blink)                                      | ✔️          | ❌        | ❌              |                                                                                                                                                                                                                                                                                                                        |
| [wg-portal](https://github.com/h44z/wg-portal)                                  | ❌          | ✔️        | ❌              |                                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                                                                |
| [Proxmox](https://www.proxmox.com/en/)                                          | ✔️           | ✔️         | ❌             | OpenID and LDAP both fully supported. Documentation [here](https://pve.proxmox.com/wiki/User_Management)                                                                                                                                                                                                              |   
| [wg-ui](https://github.com/EmbarkStudios/wg-ui)                                 | ❌          | ❌        | ✔️              | via `--auth-user-header=HEADER` option                                                                                                                                                                                                                                                                        |
| [Portainer](https://www.portainer.io/)                                          | ✔️          | ✔️        | ❌              | [Documentation](https://docs.portainer.io/admin/settings/authentication/oauth)                                                                                                                                                                                                                              |
| [Sonarr](https://sonarr.tv/)                                                    | ❌          | ❌        | ✔️              | [Docs](https://goauthentik.io/integrations/services/sonarr/)                                                                                                                                                                                                                                      |
| [Radarr](https://radarr.video/)                                                 | ❌          | ❌        | ✔️              | Can follow the guide for Sonarr                                                                                                                         |
