---
stoplight-id: tpdaidmzv03rq
tags: [Style Guides]
---

# Rule Examples: API URLs

As you think about the rules you need, consider the parts that make up API URLs:

* Protocol
* Host
* Path and path parameters
* URL parameters

![API URL Breakdown](https://stoplight.io/api/v1/projects/cHJqOjI/images/ivxyCPGgSPI)

## Protocol Rules

### Always Use HTTPS

Use this rule to enforce the HTTPS protocol for all APIs unless they are called in a local environment (localhost). 

#### OAS 3.x

Rule settings:

  - **Severity**: *Error* 
  - **Name**: *always-use-https-oas3*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Servers must use the HTTPS protocol unless using localhost.*
  - **Format** (Optional): *oas3.x*
  - **Target**: With the Stoplight Style Guide enabled, select *API > Server> URL* or add this inline target: `$.servers[*].url`
  - **Function**: *Pattern*
  - **match**: *(http:\/\/localhost)|(https).**

<!--
focus: center
bg: "#1A202C"
-->
![Always Use HTTPS - OAS 3.x](https://stoplight.io/api/v1/projects/cHJqOjI/images/Q4RMnFOWqGs)

During validation, this message is shown for URLs that do not use the HTTPS protocol.

<!--
focus: center
bg: "#1A202C"
-->
![Always Use HTTPS Validations](https://stoplight.io/api/v1/projects/cHJqOjI/images/Pm67X45r2L8)

#### OAS 2

Rule settings:

  - **Severity**: *Error* 
  - **Name**: *always-use-https-oas2*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Servers must use the HTTPS protocol.*
  - **Format** (Optional): *oas2*
  - **Target**: Add this inline target: `$.schemes.*`
  - **Function**: *enumeration*
  - **values**: `https*`

## Host Rules

### URLs Must Be Lowercase

Typically, URLs are lowercase. Requiring this as a standard helps meet industry best practices. 

Rule settings:

  - **Severity**: *Error* 
  - **Name**: *server-lowercase*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Server URL must be lowercase.*
  - **Format** (Optional): *oas3.x*
  - **Target**: With the Stoplight Style Guide enabled, select *API > Server> URL* or add this inline target: `$.servers[*].url`  
  - **Function**: *pattern*
  - **match**: `^[^A-Z]*$*`

<!--
focus: center
bg: "#1A202C"
-->
![Lowercase URLs example](https://stoplight.io/api/v1/projects/cHJqOjI/images/h9EL1S8T2Ck)

During validation, this message is shown for URLs that include uppercase characters.

<!--
focus: center
bg: "#1A202C"
-->
![Lowercase URLs validation](https://stoplight.io/api/v1/projects/cHJqOjI/images/G833bv54E7c)

### Host Name Structure

Different organizations follow different host name structures. The structure you choose does not matter as much as using the same structure consistently. This example shows how to create a rule that ensures that all host names use the `{domain}/api` structure.

Rule settings:

  - **Severity**: *Error* 
  - **Name**: *server-has-api*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Server must follow /api convention.*
  - **Format** (Optional): *oas3.x*
  - **Target**: With the Stoplight Style Guide enabled, select *API > Server> URL* or add this inline target: `$.servers[*].url`  
  - **Function**: *pattern*
  - **match**: `^\/api`

> To use a different convention, such as `api.{domain}.com`, use **notMatch** instead of **match**.

### Base Path Versioning

Similar to host name structure, there are several strategies for versioning APIs. This example shows how to enforce versioning for the base path (example: `api.example.com/v1`).

Rule settings:

  - **Severity**: *Error* 
  - **Name**: *server-version*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Server must end with a version*
  - **Format** (Optional): *oas3.x*
  - **Target**: With the Stoplight Style Guide enabled, select *API > Server> URL* or add this inline target: `$.servers[*].url` 
  - **Function**: *pattern*
  - **match**: `^.*\/v[1-9]`

  > Use `version[1-9]` to use `/version1` instead of `/v1`. 
  > 
  >Use **notMatch** if you never want to have a version on the host level.

## Path Rules

### Path Casing

There are several choices for path casing standards: kebab-case, underscore_case, camelCase, and dot.camelCase. Stoplight recommends following kebab-case, but it's most important to choose a standard and then use it consistently.

This example shows the simplest way to enforce kebab-case.

Rule settings:

  - **Severity**: *Error* 
  - **Name**: *path-casing*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Paths must be kebab-case.*
  - **Format** (Optional): *oas3.x* and *oas2*
  - **Target**: With the Stoplight Style Guide enabled, select *Path > Object* or add this inline target: `$.paths`
  - **Property**: *@key*   
  - **Function**: *casing*
  - **type**: `kebab`

<!--
focus: center
bg: "#1A202C"
-->
![Path Casing Example](https://stoplight.io/api/v1/projects/cHJqOjI/images/tEJpG8Sj8FI)

You can use also the **pattern** functions with these **match** expressions:

* For underscore_case: `^\/([a-z0-9]+(_[a-z0-9]+)*)?(\/[a-z0-9]+(_[a-z0-9]+)*|\/{.+})*$`
* For camelCase: `^/([a-z][a-zA-Z0-9]+)?(/[a-z][a-zA-Z0-9]+|/{[a-z][a-zA-Z0-9]+})*$`

### Plural Resource Names

In general, it is best to use plural nouns for resources. Because there may be exceptions, create this rule as a warning rather than an error.

This example shows how to alert users to plural resource names.

Rule settings:

  - **Severity**: *Warning* 
  - **Name**: *resource-names-plural*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Resource names should be plural.*
  - **Format** (Optional): *oas3.x* and *oas2*
  - **Target**: With the Stoplight Style Guide enabled, select *Path > Object* or add this inline target: `$.paths`
  - **Property**: *@key*   
  - **Function**: *pattern*
  - **match**: `^((\/v\d+)*((\/[\w+-]*s)(\/\{.*\})*)*)$`

### Trailing Slashes

`*/users*` and `*/users/*` are separate paths. It is considered bad practice for them to differ based only on a trailing slash. It is usually preferred to not have a trailing slash.

This example shows how to set the standard of no trailing slashes.

Rule settings:

  - **Severity**: *Warning* 
  - **Name**: *paths-no-trailing-slash*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Paths must not end with a trailing slash.*
  - **Format** (Optional): *oas3.x* and *oas2*
  - **Target**: With the Stoplight Style Guide enabled, select *Path > Object* or add this inline target: `$.paths`
  - **Property**: *@key*   
  - **Function**: *pattern*
  - **notMatch**: `\/$`

### Exclude File Extensions

Files extensions are unnecessary in URLs. Create a rule to warn users when they are included.

Rule settings:

  - **Severity**: *Error* 
  - **Name**: *paths-no-file-extensions*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Paths must not have file extensions.*
  - **Format** (Optional): *oas3.x* and *oas2*
  - **Target**: With the Stoplight Style Guide enabled, select *Path > Object* or add this inline target: `$.paths`
  - **Property**: *@key*   
  - **Function**: *pattern*
  - **notMatch**: `(JSON|json|XML|xml)`

> Add other file extensions to the **notMatch** expression as needed.

### Exclude Verbs in HTTP Methods

Verbs such as "get," "delete," and "put" should not be included in paths because this information is conveyed by the HTTP method.

Rule settings:

  - **Severity**: *Error* 
  - **Name**: *paths-no-http-verbs*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Paths must not include HTTP verbs.*
  - **Format** (Optional): *oas3.x* and *oas2*
  - **Target**: With the Stoplight Style Guide enabled, select *Path > Object* or add this inline target: `$.paths`
  - **Property**: *@key*   
  - **Function**: *pattern*
  - **notMatch**: `(GET|PUT|POST|DELETE|LIST|CREATE|REMOVE|get|put|post|delete|list|create|remove|Get|Put|Post|Delete|List|Create|Remove)`

> Add other verbs to the **notMatch** expression as needed.

### Path Versioning

This example shows how to ensure that all paths start with version numbers (example: `/v1/users/{userId}/`). 

Rule settings:

  - **Severity**: *Error* 
  - **Name**: *paths-version-number*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Paths must start with a version*
  - **Format** (Optional): *oas3.x* and *oas2*
  - **Target**: With the Stoplight Style Guide enabled, select *Path > Object* or add this inline target: `$.paths` 
  - **Property**: *@key*  
  - **Function**: *pattern*
  - **match**: `^(\/v[1-9]|\/version[1-9])`

### Avoid Special Characters

Ideally, API URLs contain only ASCII characters. This rule warns users when special characters, such as `%20`, are used in paths.

Rule settings:

  - **Severity**: *Warning* 
  - **Name**: *paths-avoid-special-characters*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Avoid using special characters in paths.*
  - **Format** (Optional): *oas3.x* and *oas2*
  - **Target**: With the Stoplight Style Guide enabled, select *Path > Object* or add this inline target: `$.paths`
  - **Property**: *@key*   
  - **Function**: *pattern*
  - **notMatch**: `^(.*)([\$&+,;=?@%]+)(.*)$`

## URL Parameter Rules

### No Query Parameters in URLs

Use this rule to alert users when query parameters are used in paths rather than defined separately in the specification.

Rule settings:

  - **Severity**: *Warning* 
  - **Name**: *paths-no-query-params*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Paths should not have query parameters in them. They should be defined separately in the OpenAPI.*
  - **Format** (Optional): *oas3.x* and *oas2*
  - **Target**: With the Stoplight Style Guide enabled, select *Path > Object* or add this inline target: `$.paths`
  - **Property**: *@key*   
  - **Function**: *pattern*
  - **notMatch**: `\?`

<!--
focus: center
bg: "#1A202C"
-->
![No Query Parameters Example](https://stoplight.io/api/v1/projects/cHJqOjI/images/dQ6eRUaZ7l0)

### Path Parameter Casing

There are several options for path parameter casing. Use this example to ensure path parameters are in camelCase and do not contain digits.

Rule settings:

  - **Severity**: *Error* 
  - **Name**: *path-parameters-camelcase*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Path parameters should be camelCase and not contain digits.*
  - **Format** (Optional): *oas3.x* and *oas2*
  - **Target**: With the Stoplight Style Guide enabled, select *Request > Parameter > Query* or add this inline target: `$..parameters[?(@.in == 'path')]`
  - **Property**: *name*   
  - **Function**: *casing*
  - **type**: *camel*
  - ** disallowDigits**: *true*

### Query Parameter Casing

This rule enforces underscore for query parameters. (Typically, you should use the same conventions for query and path parameters.)

Rule settings:

  - **Severity**: *Error* 
  - **Name**: *query-parameters-camelcase*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Query parameters should be camelCase and not contain digits.*
  - **Format** (Optional): *oas3.x* and *oas2*
  - **Target**: With the Stoplight Style Guide enabled, select *Request > Parameter > Query* or add this inline target: `$..parameters[?(@.in == 'query')]`
  _ **Property**: *name*
  - **Function**: *casing*
  - **type**: *camel*
  - ** disallowDigits**: *true*

### No Path Parameters at Operation Level

This rule ensures that path parameters are defined at the path level instead of the operation level.

Rule settings:

  - **Severity**: *Warning* 
  - **Name**: *path-parameters-on-path-only*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *Path parameters should be defined on the path level instead of the operation level.*
  - **Format** (Optional): *oas3.x* and *oas2*
  - **Target**: Add this inline target: `$.paths[*][*].parameters[?(@.in == 'path')]`
  - **Function**: *falsy*