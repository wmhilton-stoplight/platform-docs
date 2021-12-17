# Rule Examples

<!-- theme: warning -->
>**Warning**:
>Limited early access content for Shared Style Guides. Shared style guides are available on the **Professional** and **Enterprise** plans for early access participants. 

## APIs Must Be Versioned

Use the truthy function to require all APIs have version information. 

1. [Create a target](b-create-targets.md) for the `info` object: `$.info`

![style-guide-target-example.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/0eY0tOb16Oo)


2. Add a rule with these settings:

    - **Severity**: *Error* 
    - **Name**: *Version Required
    - **Message**: {{description}} (This returns your provided description in the validation list.) 
    - **Description**: *All APIs must be versioned.*
    - **Target**: Select the *info* target you created in step 1.
    - **Property**: *version* (This targets the property  name "version" located inside the info object.)
    - **Function**: *Truthy* 
    
![style-guide-rule-version-example.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/RtrbDpdsLn8)

## Path Parameters Must Adhere to Camel Case

Use the pattern function to ensure that all path parameters use Camel Case (example: myPath) and alphanumeric characters.

1. [Create a target](b-create-targets.md) for the `parameter` object. This example targets path parameters in the object: `$..parameters[?(@.in == 'path')]`.

![style-guide-path-parameter-target.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/t0JdnLpm9uU)

2. Add a rule with these settings:

    - **Severity**: *Warning* 
    - **Name**: *Path Parameter Casing*
    - **Message**: *{{property}} path parameter is not camelCase {{error}}* (This returns the last segment of the property path in the API design document, your text, and the function error.) 
    - **Description**: *Path parameters must follow Camel Case and use only alphanumeric characters.*
    - **Target**: Select the *Path Parameter* target you created in step 1.
    - **Property**: *name* (This targets the name field in the path object.)
    - **Function**: *pattern* 
    - **Match**: *^[a-z][a-zA-Z0-9]+$*
    
![style-guides-path-parameter-rule.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/iTrDSg86yls)

