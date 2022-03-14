# Rule Examples

<!-- theme: info -->
<!--Shared style guides are available on the **Professional** and **Enterprise** plans.--> 

> This feature is in preview. Reach out to nauman@stoplight.io for more information.

## APIs Must Be Versioned

Use the truthy function to require all APIs have version information. 

1. [Create a target](b-create-targets.md) for the `info` object: `$.info`

![Style Guide Target Example](https://stoplight.io/api/v1/projects/cHJqOjI/images/sQLjb2ANNqA)

2. Add a rule with these settings:

    - **Severity**: *Error* 
    - **Name**: *version-required*
    - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
    - **Description**: *All APIs must be versioned.*
    - **Target**: Select the *info* target you created in step 1.
    - **Property**: *version* (This targets the property  name "version" located inside the info object.)
    - **Function**: *Truthy* 
  
![Style Guide Version Rule Example](https://stoplight.io/api/v1/projects/cHJqOjI/images/58k0WosYbl0)

Once a style guide containing this rule is applied to an API project, the message is shown in the **Validation List** for APIs that are not versioned. Select the message to move directly to the line in the design that needs to be addressed.

![Validation for no API version](https://stoplight.io/api/v1/projects/cHJqOjI/images/k6OxHA19nZk)

## Path Parameters Must Adhere to Camel Case

Use the pattern function to ensure that all path parameters use Camel Case (example: myPath) and alphanumeric characters.

1. [Create a target](b-create-targets.md) for the `parameter` object. This example targets path parameters in the object: `$..parameters[?(@.in == 'path')]`.

![Style Guide Path Parameter Target](https://stoplight.io/api/v1/projects/cHJqOjI/images/HIVUF4DUm2o)

2. Add a rule with these settings:

    - **Severity**: *Warning* 
    - **Name**: *path-parameter-casing*
    - **Message**: *{{property}} path parameter is not camelCase {{error}}* (This returns the last segment of the property path in the API design document, your text, and the function error.) 
    - **Description**: *Path parameters must follow Camel Case and use only alphanumeric characters.*
    - **Target**: Select the *Path Parameter* target you created in step 1.
    - **Property**: *name* (This targets the name field in the path object.)
    - **Function**: *pattern* 
    - **Match**: *^[a-z][a-zA-Z0-9]+$*
    
![Style Guide Path Parameter Rule](https://stoplight.io/api/v1/projects/cHJqOjI/images/K8to0xBk3TI)

Once a style guide containing this rule is applied to an API project, the message is shown in the **Validation List** for APIs that have path parameters that do not follow the casing standard. Select the message to move directly to the line in the design that needs to be addressed.

![casing-validation.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/rjqUtPFdKdM)