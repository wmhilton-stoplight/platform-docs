# Create Targets

<!-- theme: warning -->
>**Warning**:
>Limited early access content for Shared Style Guides. Shared style guides are available on the **Professional** and **Enterprise** plans for early access participants. 

Add targets to your style guide to reference commonly used areas of API specification documents, such as OpenAPI or AsyncAPI, in rules. Use a JSON path to define the target area. 

>**Tip**
>Use our [JSONPath Plus guidelines]( https://meta.stoplight.io/docs/spectral/ZG9jOjYyMDc0NA-rulesets#jsonpath-plus) to format the JSON path. 

Reuse targets across rules in your style guide to target specific areas of the API specifications. To reference a particular property in an area, specify it when you [create a rule](c-create-rules.md). 

## Target Steps

To create a target:

1. Open a style guide project. 
2. In the Targets area of the left pane, select the plus icon next to Local to open the **Target** editor in the right pane.
3. In the **Target** editor:
    - Add a name for your target. 
    - Select the **Description** box to open a markdown editor. Add information that will be included in the style guide documentation.
    - Add a JSON path to targeta specific area of an API specification.

## Target Example
To enforce rules on paths, create an OAS3.1 target with this JSON path:

`$.paths.*`

![style-guide-paths-target.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/IfZMdlRQr0A)


[What's Next: Create Rules](c-create-rules.md)



