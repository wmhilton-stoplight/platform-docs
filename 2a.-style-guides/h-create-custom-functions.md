# Create Custom Functions

Stoplight's [core functions](https://meta.stoplight.io/docs/spectral/ZG9jOjExNg-core-functions) are intended to meet most rule validation needs, but you may need functions to solve advanced use cases. Core functions are always available in the Rule Editor.

![Stoplight core Functions](https://stoplight.io/api/v1/projects/cHJqOjI/images/Jf94y74zypY)

Custom functions are any JavaScript function compliant with the `RulesetFunction` type. See Stoplight's guidance for [writing custom functions](https://meta.stoplight.io/docs/spectral/ZG9jOjI1MTkw-custom-functions#writing-functions).

Once you've written custom functions, add them to your style guide and use them to evaluate rules.

## Add a Custom Function

![Style Guide Custom Functions](https://stoplight.io/api/v1/projects/cHJqOjI/images/wZwekKMKrbU)

To create a custom function:

1. Edit a style guide project or an API project that has a style guide enabled.
2. Select the **Styles** tab.
3. Use one of these options to add a function:
  - In the left pane from any project, select the **Add (+)** icon next to **Functions**. 
  - In a Style Guide project, select the **Add (+)** icon from project toolbar, and then select **Add Function**.
4. Use the content editor to write your function. You can also paste the function into the editor.
5. Add a function name that contains no spaces.
6. If your function accepts options, use the **Schema Editor** to describe those options. The schema options are available in the **Rule Editor** when you select the custom function.

## Apply a Custom Function

1. [Create or edit](c-create-rules.md) a rule.
2. In the **Then** section, select your custom function from the **Custom Functions** list.
3. Select function options as they apply.
