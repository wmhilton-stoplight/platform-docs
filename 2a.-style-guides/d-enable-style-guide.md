# Enable Style Guides

Projects owners, admins, and editors can enable shared style guides in any API project or in another style guide project (Professional and Enterprise plans only). This is an easy way to share rules, targets, and custom functions across style guides.

https://youtu.be/6xnRoI41v_A

Style guides are organized into two categories:

1. Workspace style guides are those that were created or imported into the workspace.
2. Public style guides are those that come from external sources. This includes the [Stoplight Style Guide](https://apistylebook.stoplight.io/docs/stoplight-style-guide), which is the set as the default style guide for each workspace.

Once you enable style guides, you can:

- [Disable inherited rules](j-disable-rules.md).
- Change the severity for enabled rules.
- Create local targets and rules.
- Use inherited targets and functions in local rules.

> Inherited targets and functions can't be modified.

To enable a style guide:

1. Edit an API project or an existing style guide project.
2. Select the **Styles** tab in the left pane.
3. On the Overview pane, select **Manage Style Guides** from the **Enabled Style Guides** page.
4. In the **Manage Style Guides** dialog:
    * Select **Preview** to open the style guide documentation in a separate browser tab.
    * Select **Enable** for one or more style guides.
    * Select **Remove** to delete [extended rulesets](https://meta.stoplight.io/docs/spectral/01baf06bdd05a-rulesets#extending-rulesets) from imported Spectral files once you no longer need them.
5. Select **Save**.

## Disable a Style Guide

You can disable style guides, including the [Stoplight Style Guide](https://apistylebook.stoplight.io/docs/stoplight-style-guide).

> Your workspace owner or admin can prevent you from [disabling default style guides](../2.-workspaces/workspace-governance.md). 

To disable a style guide:

1. Edit an API project or an existing style guide project.
2. Select the **Styles** tab in the left pane.
3. On the Overview pane, select **Manage Style Guides** from the **Enabled Style Guides** page.
4. Select the **Disable** link on an enabled style guide.

---

[What's Next: Update Style Guides](f.refresh-style-guide.md)