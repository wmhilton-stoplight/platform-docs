# Single Sign-On

Stoplight can connect with popular auth providers to simplify your authentication flows. 

## Auth Provider Support

Stoplight supports several Git providers as well as LDAP and SAML for authenticating with Stoplight.

To configure popular Git providers as auth providers, see [Git Overview](configure-git/a.configuring-git.md).

## SAML SSO

> This feature is available on the [Stoplight **Professional** plan and above](https://stoplight.io/pricing/).

Organizations that need enhanced security requirements can configure SAML SSO, allowing you to authenticate users to Stoplight with your own corporate Identity Provider (IdP).

### Prerequisites

- Log in to Stoplight as a workspace owner or admin.
- Contact the team responsible for your organization's SAML configuration for the following pieces of information that must be configured within Stoplight:
  - **SAML Entry Point URL** - This is the URL where applications integrating with a SAML IdP must first direct users.
  - **SAML Identifier Format** - Stoplight defaults to using a "persistent" name identifier format; however, some SAML providers require a specific format ("unspecified," for example).
- Some fields will also need to be configured within the SAML IdP directly. Pass along the following pieces of information to the team responsible for your organization's SAML configuration:
  - **Issuer** - This value defaults to "`stoplight`".
  <!-- markdown-link-check-disable -->
  - **Callback URL** - This value is provided during the configuration, and defaults to a value similar to **https://\<workspace\>.stoplight.io/oauth/callback**.
  <!-- markdown-link-check-enable -->
  - **Attributes** - The attributes (described below) are required by Stoplight to successfully authenticate users.

### SAML Assertion Requirements 

In addition to the items above, the following SAML attributes need to be provided in the assertion data coming to Stoplight upon successful authentication with the SAML IdP:

- **External ID** - This corresponds to the "`nameID`" field in the SAML response
- **Username** - This corresponds to one of the following fields in the SAML response (in order of precedence):
  - `userName`
  - `urn:oid:2.5.4.42`
  - `displayName`
  - `urn:oid:2.5.4.4`
- **Email** - this corresponds to either the "`email`" or
  "`urn:oid:1.2.840.113549.1.9.1`" attributes

### Configure the SAML Integration

To configure a SAML integration, navigate to your workspace
**Settings** tab and select the **SAML** integration option.

![workspace-settings-saml.png](../assets/images/workspace-settings-saml.png)

Configuration options include:

- **Name** - Customizable name users will see when authenticating.
- **Entry Point** - SAML entrypoint provided by your identity provider.
- **Identifier Format** - This SAML ID format should match what your identity provider expects. `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress` is a common format.
- **Identity Provider Public Certificate** - Public certificate provided by your identity provider. Note that this must be in string format.
- **Issuer** - Should match what the identity provider expects.
- **Callback URL** - Read-only value to be set in your identity provider configuration. This callback URL must include your workspace name. For example, `https://<workspace>.stoplight.io/oauth/callback`.

> If your SAML IdP is behind a firewall, you may need to [add Stoplight IPs to your
> allowlist](../c.troubleshooting.md#how-do-i-allow-stoplight-to-access-an-internal-git-provider).

You can enable multiple SAML integrations when authentication starts from Stoplight. Only one integration where authentication starts from an identity provider (IDP) is supported per workspace.

When you have multiple SAML integrations configured, you can specify which of these will serve as your IDP integration and the IDP badge will be displayed next to it.

![saml_idps.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/52MimIggF7g)

### SAML Integration Guides
Stoplight has tested Service Provider (SP) initiated and Identity Provider (IP) initiated flows for the following providers:

- [Azure](saml-walkthroughs/azure-integration-guide.md)
- [Google](saml-walkthroughs/google-sso-guide.md)
- [Okta](saml-walkthroughs/okta-integration-guide.md)
- [OneLogin](saml-walkthroughs/onelogin-integration-guide.md)
- [Ping](saml-walkthroughs/ping-integration-guide.md)

## LDAP

> This feature is available on the Stoplight **Professional** plan and above.

You can use a Lightweight Directory Access Protocol (LDAP) authentication server to authenticate users with Stoplight. LDAP is an open-standard protocol for use with online directory services.

<!-- markdown-link-check-disable -->

1. Navigate to the **Integrations** section in your Stoplight workspace settings. 
2. Select **LDAP**. 
3. Provide the following information:
    - **URL**: The LDAP host, for example: **ldap://ldap.example.com**. If the hostname is behind a firewall, you may need to [add Stoplight IPs to your allowlist](../c.troubleshooting.md#how-do-i-allow-stoplight-to-access-an-internal-git-provider).
    - **Bind DN**: The LDAP user that performs user lookups to authenticate other users when they sign in. This is typically a service account created specifically for third-party integrations. Use a fully qualified name, such as **cn=Administrator,cn=Users,dc=Example,dc=com**.
    - **Bind Credentials**: The password for the domain search user.
    - **Search Base**: The fully qualified Distinguished Name (DN) of an LDAP subtree you want to search for users and groups. You can add as many as you like; however, each group must be defined in the same domain base as the users that belong to it. For example: **dc=Example,dc=com**.
    - **Search Filter**: Filters can be used to restrict the numbers of users or groups that are permitted to access an application. In essence, the filter limits what part of the LDAP tree the application syncs from. Read more about writing filters [here.](https://confluence.atlassian.com/kb/how-to-write-ldap-search-filters-792496933.html)
4. Click **Install**.

<!-- markdown-link-check-enable -->

