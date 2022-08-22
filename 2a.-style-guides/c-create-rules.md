# Create Rules

The [Stoplight Style Guide](https://apistylebook.stoplight.io/docs/stoplight-style-guide) provides a set of default rules that are enabled as inherited rules for all style guides. You can, however, create your own rules to meet the needs of your API.

https://youtu.be/ZLmnV-q33X0

See these [rule examples](g-rule-examples.md) to get started.

## Add a Rule

To create a rule:

1. Edit one of these projects:
   - A style guide project so the rule can be automatically applied to API projects that use that style guide (Professional and Enterprise plans only). 
   - An API project to add the rule to that project only. 
2. Select the **Styles** tab.
3. Select the **Add** icon (+), and then select **Add Rule**.

![Add a Rule](https://stoplight.io/api/v1/projects/cHJqOjI/images/XmlF2nrOcSM)

4. In the **Rule** editor, configure the three main rule areas:
    1. [Rule Settings](#Rule-Settings)
    2. [Given Settings](#Given-Settings)
    3. [Then Settings](#Then-Settings)

![Rule Editor](https://stoplight.io/api/v1/projects/cHJqOjI/images/yGvTctKKyys)

### 1. Rule Settings

Set severity, name, the message returned during validation, and the description for documenting the rule.

- **Rule severity**

   Options are error, warning, info, and hint. When applied to an API project, the severity levels appear in the **API Design Checker** editor. You can also choose to disable a rule.

- **Name**

   Provide a short descriptive name that contains no spaces. Example: `require-description`.

- **Message**
  
   Provide the message that will appear in the **API Design Checker** as developers work with APIs. Add message text or include placeholders that are evaluated at runtime:

   - `{{error}}`: Returns the function error.
   - `{{description}}`: Returns the rule's description.
   - `{{path}}`: Returns the full path to the property in the API design document.
   - `{{property}}`: Returns the last segment of the property path in the API design document.
   - `{{value}}`: Returns the linted value in the API design document.

- **Description**

  Open the Markdown editor to add helpful information used to document the rule.

- **Format**

  Optionally set one or more formats for the rule. This is useful for overriding the global formats for the rule. OAS2 and OAS 3.x are the default formats. 

### 2. Given Settings

Set the area of the API specification the rule applies to.

- **Target**

  Select a target to specify the area of an API specification document. Targets are usually predefined and are required for each rule. Targets may be organized into [groups based on their names](b-create-targets.md#organize-targets). If you don't see a target you need, you can [add one here](b-create-targets.md). Note that inline targets can't be reused or start with the # symbol.

- **Property**

  Add properties to reference a specific entity in the target. For example, when you target the `API_Tags` area of the OAS 3.1 specification, enter `description` to enforce rules on tag descriptions.

![Add property to target](https://stoplight.io/api/v1/projects/cHJqOjI/images/bZce0HHfE1s)

### 3. Then Settings

Use Stoplight's [core functions](https://meta.stoplight.io/docs/spectral/ZG9jOjExNg-core-functions) to set the function that will evaluate your API design content. [Enable the Stoplight Style Guide](d-enable-style-guide.md) to use an additional set of custom functions.

Functions are listed in alphanumeric order.

---

[What's Next: Publish Style Guide](e.publish-style-guide.md)