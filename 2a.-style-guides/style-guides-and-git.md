---
stoplight-id: 6twy9ttde8pan
---

# Style Guides and Git

## API Projects

For Stoplight API projects that are connected to Git, files associated with style guides are stored in your repository. 

When you first push an API project to Git, you are prompted to add style guide files to your repository. The set of files depends on whether the Stoplight Style Guide is enabled or disabled. 

* **Stoplight Style Guide is enabled (default)**: `.spectral.json`,` .stoplight/styleguide.json`, and a set of custom function files. If you disable the Stoplight Style Guide, you are prompted to remove the custom function files if you had previously added them to your repository.
* **Stoplight Style Guide is disabled**: `.spectral.json` and ` .stoplight/styleguide.json`. 

These files are updated as you make changes to your project-level ruleset or inherited style guides. 

You should push the set of files and merge them into your main branch so they're available for other branches.

### Spectral Files

[Spectral rulesets](https://meta.stoplight.io/docs/spectral/ZG9jOjYyMDc0NA-rulesets) (usually called `.spectral.json`) are migrated to the Style Guide format and can be viewed and modified on the **Styles** tab. Code view isn't available at this time.

When you push changes made to this ruleset to Git, the `.spectral.json` file is updated in your repository.

Changes made to the `.spectral.json` file made outside of Stoplight aren't synced back to your style guide project. This enables you to use your `.spectral.json` file in other systems while maintaining integrity between Stoplight and the external systems.

### Ignore Style Guide Files

You can limit the number of Stoplight style guide files in your Git repository, but you should only do so if:

- You don't intend to change the default style guide, such as disabling specific rules. 
- You don't expect to [update the default style guide](f.refresh-style-guide.md) as Stoplight publishes changes.
- You don't use Spectral in your continuous integration (CI) workflow.

To persist style guides across projects, **don't** add this file to `.gitignore`:

`.stoplight/styleguide.json`

You can, however, add these files to `.gitignore`:

* `.stoplight/custom-functions`
* `.spectral.json`

Remove these files from `.gitignore` if you intend to use your CI to enforce rules when merging pull requests.

## Style Guide Projects

At this time, style guide projects are stored in Stoplight and can't be connected to Git.
