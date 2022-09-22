---
stoplight-id: 9spktiiuhvpbg
---

# Import Style Guides

You can import [Spectral](https://meta.stoplight.io/docs/spectral/e5b9616d6d50c-custom-rulesets) files that you've created or that have been shared with you. 

This is useful when you have a ruleset that's maintained outside of Stoplight. When changes are made to a Spectral ruleset, you can reimport a new version of the file to replace the old ruleset.

## Import Guidelines

- When you import Spectral files into a project, all local rules, targets, and custom functions are replaced. Inherited rules, targets, and functions aren't impacted. 
- If a rule in the import file already exists as an inherited rule, the import tries to override it. You should verify duplicates after the import.
- If your ruleset contains custom functions, first create a `zip` file that contains the Spectral file and the `.js` files that store custom functions. Then, follow the [Import Steps](#import-steps).
- The import process uses the [Spectral `functionsDir` keyword](https://meta.stoplight.io/docs/spectral/ZG9jOjI1MTkw-custom-functions#changing-directory) in the ruleset you are importing to locate custom functions. 

### Import Limitations

- You can't import JavaScript rulesets.
- The [`resolved` field](https://docs.stoplight.io/docs/spectral/e5b9616d6d50c-custom-rulesets#resolved) isn't yet supported.
- [Overrides](https://docs.stoplight.io/docs/spectral/e5b9616d6d50c-custom-rulesets#overrides) aren't yet supported. If overrides are used to disable or change the severity of a rule, remove these overrides from your Spectral file, perform the import, and then use the Rule Editor to [disable or change rule severity](j-disable-rules.md). 

## Import Steps

To import Spectral files:

1. Edit an API or style guide project.
2. Select the **Add** icon (+), and then select **Import Style Guide**.
3. Navigate to and select the Spectral file or `zip` file you want to import.
4. Confirm that you understand that your local rules, targets, and functions will be overwritten.

