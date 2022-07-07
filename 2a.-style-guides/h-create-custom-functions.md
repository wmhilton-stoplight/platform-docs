# Create Custom Functions

Stoplight's [core functions](https://meta.stoplight.io/docs/spectral/ZG9jOjExNg-core-functions) are intended to meet most rule validation needs, but you may need functions to solve advanced use cases. Core functions are always available in the Rule Editor.

![Stoplight core Functions](https://stoplight.io/api/v1/projects/cHJqOjI/images/Jf94y74zypY)

Custom functions are any JavaScript function compliant with the `RulesetFunction` type. See Stoplight's guidance for [writing custom functions](https://meta.stoplight.io/docs/spectral/ZG9jOjI1MTkw-custom-functions#writing-functions).

Once you've written custom functions, add them to your style guide and use them to evaluate rules.

## Add a Custom Function

![Style Guide Custom Functions](https://stoplight.io/api/v1/projects/cHJqOjI/images/a1LibPsCCqc)

To create a custom function:

1. Edit a style guide project or an API project that has a style guide enabled.
2. Select the **Styles** tab.
3. Select the **Add** icon (+), and then select **Add Function**.
4. Use the content editor to write your function. You can also paste the function into the editor.
5. Add a function name that contains no spaces.
6. If your function accepts options, provide a JSON Schema that describes those options.

## Adding Custom Function Options

When the custom function is selected for a rule, options can be added in the Rule Editor, as shown in the following example.

<!--
title: JSON Schema for Function Options
-->
```JSON
{
  "type": "object",
  "properties": {
    "oasVersion": {
      "type": "string",
      "enum": [
        "2",
        "3"
      ]
    },
    "schemaField": {
      "type": "string"
    },
    "type": {
      "type": "string",
      "enum": [
        "media",
        "schema"
      ]
    }
  }
}
```
The schema options are available in the Rule Editor when you select the custom function.

![Function Options in Rule Editor](https://stoplight.io/api/v1/projects/cHJqOjI/images/mywIMRpcHao)

## Apply a Custom Function

1. [Create or edit](c-create-rules.md) a rule.
2. In the **Then** section, select your custom function from the **Custom Functions** list.
3. Select function options as they apply.
