# Validate Style Guides

As you add and modify rules and targets in your style guide, the **Validate** tab alerts you to errors. You must fix errors before you can publish the style guide.

![Validation Errors](https://stoplight.io/api/v1/projects/cHJqOjI/images/3fbbzQ8w6AA)

## Common Errors

*Your Spectral ruleset contains errors*

*Error at #/rules/: must be equal to one of the allowed values*

*Error at #/rules//given: must be a non-empty array of expressions*

*Error at #/rules/invalid-rule/then: must have required property 'function'*

## Fix Common Errors

First, verify that rules and targets have all required settings. For example:

1. Targets must include valid JSON paths.
2. Rules must have a valid target, which is shown as "given" in the error.
3. Rules must have a function.