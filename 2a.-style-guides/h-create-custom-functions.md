---
internal: true
---

# Create Custom Functions

<!-- theme: info -->
<!--Shared style guides are available on the **Professional** and **Enterprise** plans.--> 

> Style guides are available for new workspaces and on request. Contact nauman@stoplight.io for more information.

Stoplight's [core functions](https://meta.stoplight.io/docs/spectral/ZG9jOjExNg-core-functions) are intended to meet most rule validation needs, but you may need functions to solve advanced use cases.

Custom functions are any JavaScript function compliant with the `RulesetFunction` type. See our guidance for [writing custom functions](https://meta.stoplight.io/docs/spectral/ZG9jOjI1MTkw-custom-functions#writing-functions).

Once you've written custom functions, add them to your style guide and use them to evaluate rules.

## Add a Custom Function

To create a custom function:

1. Edit a style guide project or a project that has a style guide enabled.
2. In the **Functions** area of the left pane, select the plus icon next to Local to open the **Functions** window.
3. Add a function name that contains no spaces.
4. Paste the function into the content box.
5. If your function accepts options, provide a JSON Schema that describes those options.
6. Select **Add Function**.

![styele-guides-custom-function.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/JmDIoEzLPOo)

> Custom functions cannot be modified after they are added to a style guide.

## Apply a Custom Function

1. [Create or edit](c-create-rules.md) a rule.
2. In the **Then** section, select your custom function from the list.
