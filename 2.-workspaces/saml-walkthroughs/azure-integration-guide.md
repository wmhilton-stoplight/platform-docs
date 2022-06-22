## Azure Configuration Guide

For Azure, you will need to create a SAML application. 

![azure-1.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/IZWyc4of9w4)

The rest of this document outlines how to configure that app.

### Azure App Configuration

#### Basic SAML Configuration:

1. Identifier (Entity ID): `https://<workspace_slug>.stoplight.io/oauth/callback`
2. Reply URL (Assertion Consumer Service URL): `https://<workspace_slug>.stoplight.io/oauth/callback` 

![azure-2.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/6BhBrvAVRGg)

#### User Attributes & Claims:

<!-- theme: info -->
> follow the [guide](https://meta.stoplight.io/docs/platform/ZG9jOjQ1NTQxMg-single-sign-on#saml-assertion-requirements) in platform docs for configuring parameters. Below are the minimum required parameters to get this working.
1. mail --> user.mail

![azure-3.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/SdwNfJmA8lc)

### Stoplight Integration Configuration

1. Entry Point --> `Login URL` from "Set Up \<Your App Name\>" section
2. Identifier Format --> `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress`
3. Identity Provider Public Certificate --> `Certificate (Base64)` from "SAML Signing Certificate Section"
4. Issuer --> `https://<workspace_slug>.stoplight.io/oauth/callback`
5. Request Specific Authentication Context --> `Enabled`

![azure-4.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/JG0l3VLtsw0)

<!-- theme: info -->
> Azure only lets you download the certificate in a `.cer` file. To extract the contents of the certificate to save in Stoplight you can run the following command:
> ```
>openssl x509 -in /path/to/downloaded/azure.cer -out stoplight.pem
>```
> The certificate contents will be in a `stoplight.pem` file wherever you ran the command from.