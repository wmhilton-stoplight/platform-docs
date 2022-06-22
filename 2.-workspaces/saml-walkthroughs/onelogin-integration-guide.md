## OneLogin Configuration Guide

For OneLogin you will need to create a SAML Test Connector (Advanced) app. The rest of this document outlines how to configure that app. 

### OneLogin App Configuration

#### Configuration Tab:

1. ACS (Consumer) URL Validator: `https://<workspace_slug>.stoplight.io/oauth/callback`
2. ACS (Consumer) URL: `https://<workspace_slug>.stoplight.io/oauth/callback`
3. SAML initiator: `OneLogin` (for IDP initiated) or `Service Provider` (for SP initiated)
4. SAML nameID format: `Email`

![onelogin-1.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/oAHPyagK9I0)

#### Parameters Tab:

<!-- theme: info -->
> follow the [guide](https://meta.stoplight.io/docs/platform/ZG9jOjQ1NTQxMg-single-sign-on#saml-assertion-requirements) in platform docs for configuring parameters. Below are the minimum required parameters to get this working.

1. NameID --> Email
2. mail --> Email

![onelogin-2.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/oMqREXnXI3w)

### Stoplight Integration Configuration

1. Entry Point --> `SAML 2.0 Endpoint (HTTP)` from the SSO Tab in OneLogin App
2. Identifier Format --> `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress`
3. Identity Provider Public Certificate --> `X.509 Certificate` from the SSO Tab in OneLogin App
4. Issuer --> `Issuer URL` fromthe SSO Tab in OneLogin App
5. Request Specific Authentication Context --> `Enabled`

![onelogin-3.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/xE3z815H6ys)




