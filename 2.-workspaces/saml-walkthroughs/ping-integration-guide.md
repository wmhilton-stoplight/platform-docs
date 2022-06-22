## Ping Configuration Guide

For Ping, you will need to create a SAML application going through the **Advanced Configuration** setup menu. 

![ping-1.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/Cub8kWi6gas)

The rest of this document outlines how to configure that app.

### Ping App Configuration

#### Configuration Tab:

1. ACS URLS: `https://<workspace_slug>.stoplight.io/oauth/callback`
2. Entity ID: `stoplight`
3. Subject NameID Format: `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress`
4. Assertion Validity Duration (In Seconds): `60`

![ping-2.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/DUyvDRaN6WE)

#### Attribute Mappings Tab:

<!-- theme: info -->
> follow the [guide](https://meta.stoplight.io/docs/platform/ZG9jOjQ1NTQxMg-single-sign-on#saml-assertion-requirements) in platform docs for configuring parameters. Below are the minimum required parameters to get this working.
1. User ID --> saml_subject
2. Email Address --> mail

![ping-3.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/D6WzA50UDdE)

### Stoplight Integration Configuration

1. Entry Point --> `Single SignOn Service` from the Configuration Tab in Ping App
2. Identifier Format --> `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress`
3. Identity Provider Public Certificate --> `Download Signing Certificate` from the Configuration Tab in Ping App. Select the `X509 PEM (.crt)` format
4. Issuer --> `stoplight` (this must match the Entity ID configured in the Ping app)
5. Request Specific Authentication Context --> `Enabled`

![ping-4.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/WNFOxTbVbKM)

<!-- theme: info -->
> Ping only lets you download the certificate in a `.crt` file. To extract the contents of the certificate to save in Stoplight you can run the following command:
> ```
>openssl x509 -in /path/to/downloaded/ping.crt -out stoplight.pem
>```
> The certificate contents will be in a `stoplight.pem` file wherever you ran the command from.


