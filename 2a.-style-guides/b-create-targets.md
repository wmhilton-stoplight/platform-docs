# Create Targets

The [Stoplight Style Guide](https://apistylebook.stoplight.io/docs/stoplight-style-guide) provides a set of default targets, but you can add custom targets to reference commonly used areas of API specification documents, such as OpenAPI or AsyncAPI, in rules. 

Use a JSON path to define the target area. You can add simple targets or more complex targets with multiple specification types (OAS 3.1 and AsyncAPI 2.0, for example) and multiple JSON paths for each specification type.

>**Tip**
>Use these [JSONPath Plus guidelines]( https://meta.stoplight.io/docs/spectral/ZG9jOjYyMDc0NA-rulesets#jsonpath-plus) to format the JSON path.

Reuse targets across rules in your style guide to target specific areas of the API specifications. To reference a particular property in an area, specify it when you [create a rule](c-create-rules.md).

## Add a Target

To create a local target:

1. Edit a style guide project or a project that has a style guide enabled.
2. In the **Targets** area of the left pane, select the **Add** icon (+) to open the **Target** editor.
3. In the **Target** editor:
    - Add a name that contains no spaces. Separate words with underscores to [organize targets](#organize-targets) into groups.
    - Select **Add markdown here** in the **Description** to open a markdown editor and add a description so others understand when to use the target.
    - Select **Add new format**, and then select a specification type (oas3.x, asyncapi2, etc.).
    - Add a JSON path to target a specific area of an API specification.
4. Add additional formats and paths as needed.

<!--
focus: center
bg: "#1A202C"
-->
![Style Guide Targets](https://stoplight.io/api/v1/projects/cHJqOjI/images/GogSfzgUbXY)

## Organize Targets

Separate words in target names to organize targets into groups. This makes it easier to find and select targets in the **Rule Editor**.

To see examples of target groups:

1. Enable the [Stoplight Style Guide](d-enable-style-guide.md) in your project.
2. In the left pane, scroll to the **Request** section of inherited targets.

<!--
focus: center
bg: "#1A202C"
-->
![Target Naming Structure](https://stoplight.io/api/v1/projects/cHJqOjI/images/5ZoBt5qoaIs)

3. In the left pane, select the **Add** icon (+) next to **Rules** to open the **Rule Editor**.
4. Select the **Targets** menu, and notice the organization for targets staring with **Request_**:
    * `Request_`: Organizes the targets under a parent heading.
    * `Parameter_`: Organizes the targets under a sub-heading.

<!--
focus: center
bg: "#1A202C"
-->
![Target Name Results](https://stoplight.io/api/v1/projects/cHJqOjI/images/w4zXSh3fHkU)

---

[What's Next: Create Rules](c-create-rules.md)