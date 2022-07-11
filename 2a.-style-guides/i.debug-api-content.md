# Debug Rules

Once you create rules, debug them with JSON-formatted API content. This enables you to find and fix rule errors quickly and easily.

You can:
* Debug rules in projects that have a style guide enabled or for style guide projects themselves.
* Debug an entire JSON file or part of a file.

https://youtu.be/Hh5nRmg5bIw

To debug API content:

1. Edit a style guide project or a an API project that has a style guide enabled.
2. Select the **Styles** tab.
3. Select a rule from the left side panel.
4. Select **Debug**.
5. Example content is provided in the **Debug** window, but you can add your own JSON content to validate your rules.

If the JSON violates the selected rule, the rule's message is shown in the **Validation List**.

![Debug Rules](https://stoplight.io/api/v1/projects/cHJqOjI/images/lS1TIbBltPo)

If your rule is invalid, you receive this error: "Your Spectral ruleset contains errors." In this case, you need to adjust the rule.