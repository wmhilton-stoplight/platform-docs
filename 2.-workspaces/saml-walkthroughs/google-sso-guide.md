---
stoplight-id: 05fkwr5veo1ag
---

## Google SSO Configuration Guide

For Google SSO, you will need to create a SAML application. 

![google-sso.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/iH3BBZW5X9g)


### Google SSO App Configuration

#### Basic SAML Configuration:

1. Identifier (Entity ID): `stoplight`
2. Reply URL (Assertion Consumer Service URL): `https://<workspace_slug>.stoplight.io/oauth/callback` 

![google-sso-2.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/rlw0uyHRwcA)

#### User Attributes & Claims:

<!-- theme: info -->
> Follow the [guide](https://meta.stoplight.io/docs/platform/ZG9jOjQ1NTQxMg-single-sign-on#saml-assertion-requirements) in platform docs for configuring parameters. Below are the minimum required parameters to get this working.
1. mail --> Primary email

![google-sso-3.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/OmiGzVj8NQo)

### Stoplight Integration Configuration

1. Entry Point --> `SSO URL` from "Download Metadata" form
2. Identifier Format --> `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress`
3. Identity Provider Public Certificate --> `Certificate` from "Download Metadata" form
4. Issuer --> `stoplight`
5. Request Specific Authentication Context --> `Enabled`

![google-sso-4.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/kt4TxTCm4Rs)

<!-- theme: info -->
> Please note that it could take up to several hours for the app's settings to fully propagate throughout Google's system. During this time, you may receive errors like `app_not_configured_for_user` or `not_a_saml_app` while attempting to login using this new SAML app.