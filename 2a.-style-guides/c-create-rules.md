# Create Rules

The [Stoplight Style Guide](https://apistylebook.stoplight.io/docs/stoplight-style-guide) provides a set of default rules that are enabled as inherited rules for all style guides. You can, however, create your own rules to meet the needs of your API.

https://youtu.be/ZLmnV-q33X0

See these [rule examples](g-rule-examples.md) to get started.

## Add a Rule

To create a rule:

1. Edit one of these projects:
   - A style guide project so the rule can be automatically applied to API projects that use that style guide ([Professional and Enterprise plans only](https://stoplight.io/pricing)). 
   - An API project to add the rule to that project only. 
2. Select the **Styles** tab.
3. In the left pane, select the **Add (+)** icon next to **Rules**. (In a Style Guide project, select the **Add (+)** icon from project toolbar, and then select **Add Rule**.)
4. In the **Rule** editor, configure the three main rule areas:
    1. [Rule Settings](#Rule-Settings)
    2. [Given Settings](#Given-Settings)
    3. [Then Settings](#Then-Settings)

![Rule Editor](https://stoplight.io/api/v1/projects/cHJqOjI/images/lofFeZwM2UY)

### 1. Rule Settings

Set severity, name, the message returned during validation, and the description for documenting the rule.

- **Rule severity**: Options are error, warning, info, and hint. When applied to an API project, the severity levels appear in the **API Design Checker** editor. You can also choose to disable a rule.

- **Name**: Provide a short descriptive name that contains no spaces. Example: `require-description`.

- **Message**: Provide the message that will appear in the **API Design Checker** as developers work with APIs. Add message text or include placeholders that are evaluated at runtime:

   - `{{error}}`: Returns the function error.
   - `{{description}}`: Returns the rule's description.
   - `{{path}}`: Returns the full path to the property in the API design document.
   - `{{property}}`: Returns the last segment of the property path in the API design document.
   - `{{value}}`: Returns the linted value in the API design document.

- **Description**: Open the Markdown editor to add helpful information used to document the rule. API designers can select the **book** icon in the **API Design Checker** to see the rule documentation, so consider adding examples and other guidance.

- **Format**: Optionally set one or more formats for the rule. This is useful for overriding the global formats (OAS2 and OAS 3.x) for the rule.

### 2. Given Settings

Select a **target** to specify an area of an API specification document. Targets are usually predefined and are required for each rule. Targets may be organized into [groups based on their names](b-create-targets.md#organize-targets). If you don't see a target you need, you can [add one here](b-create-targets.md). Note that inline targets can't be reused or start with the # symbol.

### 3. Then Settings

Use **Then** settings to further refine the rule's scope (optional) and select a function that determines how design content will be evaluated. For example, the core function `truthy` checks for a value that's not `false`, `""`, `0`, `null`, or `undefined`.

You can apply multiple **Then** settings per rule. This enables you to apply multiple functions to a rule rather than create a rule for each function you need. For example, you may want to apply the `truthy` function and a `length` function to the same property.

You must have at least one **Then** setting.

- **Property**: Add properties to reference a specific entity in the specified target. For example, when you target the `API_Tags` area of the OAS 3.1 specification, enter `description` to enforce rules on tag descriptions.

- **Function**: Select a function(required). You can:
   -  Use Stoplight's [core functions](https://meta.stoplight.io/docs/spectral/ZG9jOjExNg-core-functions), which are available for every style guide. 
  - [Enable the Stoplight Style Guide](d-enable-style-guide.md) to use an additional set of custom functions. Functions are listed in alphanumeric order.
  - [Create your own functions](h-create-custom-functions.md).

---

[What's Next: Publish Style Guide](e.publish-style-guide.md)