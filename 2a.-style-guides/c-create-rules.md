# Create Rules

<!-- theme: info -->
<!--Shared style guides are available on the **Professional** and **Enterprise** plans.--> 

<!-- focus: false -->
![Feature Preview](../assets/images/badge-preview-small.png)

*Style guides are available for new workspaces and on request. Contact nauman@stoplight.io for more information.*

The [Stoplight Style Guide](https://apistylebook.stoplight.io/docs/stoplight-style-guide) provides a set of default rules, but you can easily create your own rules to meet the needs of your API.

https://youtu.be/ZLmnV-q33X0

See our [rule examples](g-rule-examples.md) to get started.

## Add a Rule

To create a rule:

1. Edit a style guide project or a project that has a style guide enabled.
2. In the **Rules** area of the left pane, select the plus icon next to Local to open the **Rules** editor in the right pane.
3. Configure the three main rule areas:
    - [Rule Settings](#Rule-Settings)
    - [Given](#Given-Settings)
    - [Then](#Then-Settings)

### Rule Settings

Set severity, name, the message returned in validation, and the description for documenting the rule.

- **Rule severity**
   Options are error, warning, information, and hint. When applied to an API project, the severity levels appear in the **API Design** editor. 
   ![Rule severity icons](../assets/images/rule-severity-indicators.png)
   You can also choose to disable a rule.

- **Name**

   Provide a short descriptive name that contains no spaces. Example: `require-description`.

- **Message**
  
   Provide the message that will appear in the validation results list in the **API Design** editor. Add message text or include placeholders that are evaluated at runtime:

   - `{{error}}`: Returns the function error.
   - `{{description}}`: Returns the rule's description.
   - `{{path}}`: Returns the full path to the property in the API design document.
   - `{{property}}`: Returns the last segment of the property path in the API design document.
   - `{{value}}`" Returns the linted value in the API design document.

- **Description**

  Open the Markdown editor to add helpful information used to document the rule.

### Given Settings

Set the area of the API specification the rule applies to.

- **Target**

  Select a target to specify the area of an API specification document. Targets are predefined and required for each rule. See [Create Targets](b-create-targets.md).

- **Property**

  Add properties to reference a specific entity in the target. For example, when you target the `API_Tags` area of the OAS 3.1 specification, enter `description` to enforce rules on tag descriptions.

![Add property to target](https://stoplight.io/api/v1/projects/cHJqOjI/images/bZce0HHfE1s)

### Then Settings

Use Stoplight's [core functions](https://meta.stoplight.io/docs/spectral/ZG9jOjExNg-core-functions) to set the function that will evaluate your API design content.

[What's Next: Publish Style Guide](e.publish-style-guide.md)