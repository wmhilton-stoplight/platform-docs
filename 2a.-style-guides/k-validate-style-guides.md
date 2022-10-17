# Validate Style Guides

As you add and modify rules, targets, and functions in your style guide, the **Validate** tab alerts you to errors. 

For style guide projects only, you must fix errors before you can publish the style guide. You can publish API projects that contain style guide errors, but doing so isn't recommended.

## Find Errors

Enable the **All Errors** option to list all errors in the style guide. When disabled, you'll only see errors for the rule, target, or function you've selected.

1. On the **Validate** tab, enable the **All Errors** option.
2. Hover over the information icon at the right of each error to see the location of the error. 

In the following example, the error can be found in the `given` section of the `path-casing-rule`. 

![Find validation errors](https://stoplight.io/api/v1/projects/cHJqOjI/images/J4HcHTdcJUo)

> Rules, targets, and functions must have names or the error location isn't shown. In this case, disable **All Errors** and select each item in the left pane until you find the items that have validation errors.

## Common Errors

The most common errors occur when you add rules, targets, and functions, but don't configure them.

Here are examples of errors you may see:

* **Your Spectral ruleset contains errors**: Indicates that there are errors in your style guide.
* **Targets must have at least a single alias definition**: Indicates that a target is missing a JSON Path. 
* **Must be a valid format**: Indicates that the provided JSON Path has an invalid format.
* **Function needs to be selected and point to an existing function**: Indicates that a function isn't selected or the selected function isn't valid.

## Fix Common Errors

Verify that rules and targets have all required settings. 

For example:

1. Rules must have a valid target.
2. Targets must have valid JSON paths.
3. Rules must have at least one valid function.

