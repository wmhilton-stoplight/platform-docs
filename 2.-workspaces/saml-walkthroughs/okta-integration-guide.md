## Okta Configuration Guide
For Okta you will need to create a SAML 2.0 application. 

![okta-1.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/Qzzou7QTGh8)


The rest of this document outlines how to configure that app.

### Okta App Configuration
#### SAML Settings:
1. Single sign on URL: `https://<workspace_slug>.stoplight.io/oauth/callback`
2. Audience URI (SP Entity ID): `https://<workspace_slug>.stoplight.io/oauth/callback`
2. Name ID format: `EmailAddress`

![okta-2.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/XsRriv240lY)


#### Attribute Statements (Optional):
<!-- theme: info -->
> follow the [guide](https://meta.stoplight.io/docs/platform/ZG9jOjQ1NTQxMg-single-sign-on#saml-assertion-requirements) in platform docs for configuring parameters. Below are the minimum required parameters to get this working.
1. mail --> user.email

![okta-3.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/vILKgAP5SGo)


### Stoplight Integration Configuration
<!-- theme: info -->
> All of the following values come from the `View Setup Instructions` area of the Okta SAML app.
>
> ![okta-4.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/pBhnKHVfI0k)


1. Entry Point --> `Identity Provider Single Sign-On URL`
2. Identifier Format --> `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress`
3. Identity Provider Public Certificate --> `X.509 Certificate`
4. Issuer --> `Identity Provider Issuer`
5. Request Specific Authentication Context --> `Enabled`

<!-- markdown-link-check-disable-next-line -->
![okta-5.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/yGHWQcT5mCs)





