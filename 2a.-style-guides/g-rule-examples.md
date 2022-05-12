# Rule Examples

The [Stoplight Style Guide](https://apistylebook.stoplight.io/docs/stoplight-style-guide) provides a set of targets and rules for all API projects. You can use the rules as-is, disable them, or create your own rules. The examples in this topic explain how to use the provided targets to create custom rules.

## APIs Must Be Versioned

Use the provided `API_Document` target and the `truthy' function to require all APIs have version information. 

Add a rule with these settings:

  - **Severity**: *Error* 
  - **Name**: *version-required*
  - **Message**:  *{{description}}* (This returns your provided description in the validation list.) 
  - **Description**: *All APIs must be versioned.*
  - **Target**: Select *API_Document*.
  - **Property**: *version* (This targets the property  name "version" located inside the info object.)
  - **Function**: *Truthy* 
  
![Style Guide Version Rule Example](https://stoplight.io/api/v1/projects/cHJqOjI/images/8M9DdeCUZyM)

Once a style guide containing this rule is applied to an API project, the message is shown in the **Validation List** for APIs that are not versioned. Select the message to move directly to the line in the design that needs to be addressed.

![Validation for no API version](https://stoplight.io/api/v1/projects/cHJqOjI/images/k6OxHA19nZk)

## Path Parameters Must Adhere to Camel Case

Use the provided `Parameter_All_Item` target and the `casing` function to ensure that all path parameters use Camel Case (example: myPath) and alphanumeric characters.

Add a rule with these settings:

  - **Severity**: *Warning* 
  - **Name**: *path-parameter-casing*
  - **Message**: *{{property}} path parameter is not camelCase {{error}}* (This returns the last segment of the property path in the API design document, your text, and the function error.) 
  - **Description**: *Path parameters must follow Camel Case and use only alphanumeric characters.*
  - **Target**: Select *Request_Parameter_All*
  - **Property**: *name* (This targets the name field in the path object.)
  - **Function**: *casing* 
  - **Type**: camel
    
![Style Guide Path Parameter Rule](https://stoplight.io/api/v1/projects/cHJqOjI/images/AEbmAKpH6lA)

Once a style guide containing this rule is applied to an API project, the message is shown in the **Validation List** for APIs that have path parameters that do not follow the casing standard. Select the message to move directly to the line in the design that needs to be addressed.

![Case Validation](https://stoplight.io/api/v1/projects/cHJqOjI/images/rjqUtPFdKdM)

## Response Headers Must Include a Rate Limit

Create a custom target and use the `truthy` function to ensure that rate limits are added to response headers to control the number of allowed requests in the current period.

1. [Create a target](b-create-targets.md) for the `response` object. This example targets all responses in an API: `$..responses.*`. In this example, we created a target for two formats: oas3.1 and oas3.0.

![Response Targets](https://stoplight.io/api/v1/projects/cHJqOjI/images/J2RbvdeFmNQ)

2. Add a rule with these settings:
      
   - **Severity**: *Error*
   - **Name**:  rate-limiters
   - **Message**: *{{description}}; missing {{property}}* (This returns the description you provide, the word "missing," and the missing property.)
   - **Description**: *Responses must include X-Rate-Limit headers.*
   - ***Target**: Select the *responses* target you createad in step 1.
   - **Property**: *headers.ratelimit-limit* (This targets the  X-Rate-Limit-Limit field in the response header.)
   - **Function**: *Truthy* 

![Rate Limit Rule](https://stoplight.io/api/v1/projects/cHJqOjI/images/IhogHCC6SOw)

Once a style guide containing this rule is applied to an API project, the message is shown in the **Validation List** for each response that does not include rate limits. Select the message to move directly to the line in the design that needs to be addressed.

[What's Next: Publish Style Guides](e.publish-style-guide.md)