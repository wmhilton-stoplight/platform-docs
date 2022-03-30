# Create Targets

<!-- theme: info -->
<!--Shared style guides are available on the **Professional** and **Enterprise** plans.--> 

> This is a limited access feature. Reach out to nauman@stoplight.io for more information.

The [Stoplight Style Guide](https://apistylebook.stoplight.io/docs/stoplight-style-guide) provides a set of default targets, but you can add custom targets to reference commonly used areas of API specification documents, such as OpenAPI or AsyncAPI, in rules. Use a JSON path to define the target area. You can add simple targets or more complex targets with multiple specification types (OAS 3.1 and asyncapi 2.0, for example) and multiple JSON paths for each specitition type.

>**Tip**
>Use our [JSONPath Plus guidelines]( https://meta.stoplight.io/docs/spectral/ZG9jOjYyMDc0NA-rulesets#jsonpath-plus) to format the JSON path.

Reuse targets across rules in your style guide to target specific areas of the API specifications. To reference a particular property in an area, specify it when you [create a rule](c-create-rules.md).

## Add a Target

To create a target:

1. Edit a style guide project or a project that has a style guide enabled.
2. In the **Targets** area of the left pane, select **+ Add** to open the **Target** editor.
3. In the **Target** editor:
    - Add a name that contains no spaces.
    - Select **Add markdown here** in the **Description** to open a markdown editor and add a description so others understand when to use the target.
    - Select **Add new format**, and then select a specification type (oas3.x, asyncapi2, etc.).
    - Add a JSON path to target a specific area of an API specification.
4. Add additional formats and paths as needed.

![style-guide-targets.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/KSsNYD2pDHA)

## Target Example
To enforce rules on paths, create an OAS3.x target with this JSON path:

`$.paths.*`

![style-guide-paths-target.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/agsDhzXTkHE)

[What's Next: Create Rules](c-create-rules.md)