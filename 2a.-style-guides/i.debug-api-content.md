# Debug Rules

Once you create rules, debug them with JSON-formatted API content. This enables you to find and fix rule errors quickly and easily.

You can:
* Debug rules in projects that have a style guide enabled or for style guide projects themselves.
- Debug all rules or a single rule.
* Debug an entire JSON file or part of a file.

https://youtu.be/Hh5nRmg5bIw

To debug rules:

1. Edit a style guide project or a an API project that has a style guide enabled.
2. Select the **Styles** tab.
3. Select a rule from the left side panel.
4. Select the **Debug** tab, and then:
   * To debug a single rule, clear the **Debug all rules** check box, and then select a rule.
   * To debug all rules, select the **Debug all rules** check box.
5. Example content is provided, but you can add JSON content to validate your rules.

The **Validation Results** lists shows a message for any rule that isn't valid based on the provided JSON. Hover over the book icon for each message to see which rule is generating the message.

![Debug Rules](https://stoplight.io/api/v1/projects/cHJqOjI/images/lS1TIbBltPo)

> If your rule is invalid, this error is shown: "Your Spectral ruleset contains errors." In this case, you need to adjust the rule.