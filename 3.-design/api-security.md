# API Security

The OpenAPI specification allows API designers to define authentication and authorization as part of their machine-readable API description through security scheme definitions and security requirements. Stoplight supports all OpenAPI security features.

A security scheme is a global definition with a name that designates an authentication method available for the API. It's possible to define multiple schemes if, for example, an API supports both Basic Authentication and OAuth. There can even be various schemes of the same type.

A security requirement, on the other hand, can exist both globally for the entire API or on an operation level. It matches the API as a whole or the individual API operation to one or more of the previously defined security schemes. Developers can use this to specify different levels of authorization explicitly, for example, by making read requests available without authentication, but requiring OAuth for write requests.

## Create Security Schemes

<!-- The options in this section match the UI but go againt Vale rules -->

![Add Security Scheme](https://stoplight.io/api/v1/projects/cHJqOjI/images/pMCQSvLUc7g)

To define security schemes:

1. From the**API Overview** selection, select the **Add (+)** icon next to **Security**.
2. Select one of these scheme types, which are explained in the following sections:
   - apiKey
   - oauth2
   - http
   - openIdConnect
3. In the **Key** field, provide a name for your scheme. The key is used to reference the scheme in a security requirement and must be unique within the API.
4. Optionally, select the **Description** button on the right to add more information about your scheme.

### API Keys

An API key is a single token sent to the API server that the user has retrieved through an out-of-band mechanism. API keys can be a query parameter, a custom HTTP header, or a cookie.

Use these API key recommendations:

- Use **cookie** when a web application uses your API in the browser and you can use cookies for session management.
- Use **query** when your API is mostly exposing public data or doesn't have strict security constraints and may be used in environments where developers can only specify a URL but no custom headers.
- In all other cases, use **header** as the best practice that follows proper HTTP semantics.

![API Key](https://stoplight.io/api/v1/projects/cHJqOjI/images/bHYvQu2AxRY)

To create an API key:

1. Select the **apiKey** scheme type. 
2. Use the right menu to toggle between **query**, **header**, and **cookie**.
3. Add a name for the query, cookie, or header name.

### OAuth 2

OAuth is an open authentication standard defined by [RFC6749](https://tools.ietf.org/html/rfc6749) and [RFC6750](https://tools.ietf.org/html/rfc6750). OAuth also uses the standard HTTP _Authorization_ header to send a credential known as bearer token but also defines various flows for retrieving this bearer token. You can enter the configuration for the flows into your OpenAPI specification and various OpenAPI tools can use this information to assist the user in going through them.

If you are unsure which flows your API should support or which ones to add, here is a short guide:

- Most APIs use OAuth because authorized API calls need a user context. For this purpose,  **authorizationCode** flow is the most common OAuth flow.
- If an application consuming the API is only a browser-based application without a backend, you may want to support the **implicit** flow. However, there are OAuth extensions like PKCE that assist in implementing the more secure **authorizationCode**_ flow for these applications, so you may not need **implicit**.
- If your application uses OAuth for API calls without a user context, you can add **clientCredentials**.
- Don't use the **password** flow unless you understand the security implications.

You can learn more about these flows on the [OAuth website](https://oauth.net/).

> **Hint:**
> If your API uses OAuth 1, select the **http** scheme type, and then select **oauth** as a subtype.

![OAuth Configuration](https://stoplight.io/api/v1/projects/cHJqOjI/images/1TXQEE6KFfY)

To create an Oauth 2 key:

1. Select the **oauth2** scheme type. 
2. Select one or more of the following flow types: **implicit**, **password**, **clientCredentials**, and **authorizationCode**. 
3. Select the **OAuth2 Flow** icon to add information for selected flows:
   - **Implicit** - Provide Refresh URL and Authorization URL.
   - **Password** and **clientCredentials** - Provide a refresh URL and token URL.
   - **AuthorizationCode** - Provide a refresh URL, authorization URL, and token URL. (The **Refresh URL** is only required if your OAuth server issues refresh tokens.)
4. For each Oauth 2 flow, add scopes with a name and description. Scopes specify certain access rights for your API. You should add at least one scope for your API, but you can add as many as you want.

![Additional OAuth Security](https://stoplight.io/api/v1/projects/cHJqOjI/images/Vd2N2eBVSM4)

### OpenID Connect

OpenID Connect is a set of specifications that extend OAuth 2. Most relevant in the context of OpenAPI is a feature specified in [OpenID Connect Discovery](https://openid.net/connect/) that allows dynamic retrieval of OpenID provider information, including OAuth 2 attributes like URLs, supported flows, and scopes.

![OpenID Connect Configuration](https://stoplight.io/api/v1/projects/cHJqOjI/images/efVbwqcHgEI)

To create an OpenID Connect key:

1. Select the **openIdConnect** scheme type. 
2. Provide the OpenID Connect URL.

### HTTP Authentication

HTTP authentication uses the standard HTTP Authorization header defined in [RFC7235](https://tools.ietf.org/html/rfc7235).

OpenAPI and, by extension, Stoplight support all the [schemes registered at IANA](https://www.iana.org/assignments/http-authschemes/http-authschemes.xhtml). 

While OpenAPI supports the different variants of HTTP authentication, the majority of APIs use **basic**. With basic authentication, an API client sends the combination of a username and a password in the Authorization header. The method for retrieving the username and password isn't part of the OpenAPI description.

![HTTP Auth Configuration](https://stoplight.io/api/v1/projects/cHJqOjI/images/mYOOyhiBk4Q)

To create an HTTP key:

1. For HTTP authentication, select the **http** scheme type.
2. Select an HTTP authentication scheme.

## Specify Global Security

You can specify global security requirements in the API Overview. Follow these global security requirements:

- If you define multiple schemes, the API consumer must follow one of them.
- Global security applies to all API operations unless you define a specific security requirement for them.

To add a global security requirement:

1. From the**API Overview** selection, select the **Add (+)** icon next to **Global Security**.
2. Select **+ Add global security**.
3. Choose a security scheme.
4. If the selected security scheme uses **OAuth 2** and you have defined scopes, optionally enter the scopes required for API access in the scopes input field. Note that **all** scopes must be authorized in the flow.

## Specifying Security Requirements for Operations

You can specify security requirements for every operation in your API. This overrides any global security requirement you may have specified. If you don' specify a security requirement for an operation and there are no global security requirements, the operation doesn't require authentication.

To add a requirement to an operation:

1. Select the path, and then select **+ Security**.
2. Select **+ Add operation security**.
3. Select a security scheme.
4.  If the selected security scheme uses **OAuth 2** and you have defined scopes, optionally enter the scopes required for API access in the scopes input field. Note that **all** scopes must be authorized in the flow.

You can also remove a global security requirement if you want to describe an operation that needs no authentication. 

To remove global security:

1. Select the path, and then select **+ Security**.
2. Select **Disable security for operation**.

## Documenting API Security

Your OpenAPI description provides the input for autogenerated API reference documentation, whether you use Stoplight for this purpose or another, third-party tool. That documentation automatically includes information about the security schemes that you support and which endpoints require authentication.

However, to enable consumers to integrate your API successfully, you need to provide some additional information not included in your OpenAPI description:

- For the _apiKey_ scheme, inform consumers where they can generate or retrieve their API key. If API keys expire or need to rotate, make sure to communicate that.
- For the _oauth2_ scheme, inform consumers where they can get their client ID and secret. You should also let them know about the validity of authorization codes and access tokens. If your server issues refresh tokens, inform about this fact and what their validity is.
- For the _http_ scheme and most of its subtypes like _basic_, inform consumers where they can get their username and password. Make sure to stress whether these are the same credentials that they use to log in to the frontend or whether they're different credentials.

You can include this information as part of a quick start guide or as a separate authentication document. If you write these documents in Markdown, you can use Stoplight Studio to create and edit them.