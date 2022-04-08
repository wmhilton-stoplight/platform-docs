# Project Settings

Use project settings to change the name and other project information, move a project to a group, and manage web project versions and Git branches, and more.

Project owners and administrators can modify project settings.

Use one of these methods to open the **Project Settings** page:

* From the projects list, select a project, and then select the **Project Settings** link in the right pane.
* From the workspace sidebar, select a project, and then select the project gear icon.

## Project Basics

* **Display Name**: Use to change the name that appears on the workspace sidebar, projects list, etc.

* **Slug**: The value used in project URLs. Project slugs must be unique in a workspace.

* **ID**: Used to identify the project by the [Element Dev Portal](https://meta.stoplight.io/docs/elements/ZG9jOjEyMDU2Njc2-introduction-to-elements-dev-portal).

* **Tagline**: Text here is shown below the project name in the workspace sidebar.

* **Icon Name**: Change the icon by typing a keyword (example: coffee). If an icon matching the keyword is available, the icon changes.

* **Icon Color**: Add an icon color in hex format.

* **Group** (Professional and Enterprise only): Optionally, select a [group](../2.-workspaces/m.groups.md) for the project. Groups are used to organize sets of projects.

## Versions

> This feature is available on the Stoplight **Starter** plan and above.

You can create versions for Stoplight projects, which are also referred to as web projects.

Since Stoplight projects are not tied to  Git, versions are useful for publishing distinct sets of content based on criteria of your choosing. This enables you to update content in one version without impacting content in others. The most common use is to version content based on a numbering or naming scheme (V1, V2, V2.2, etc.).

Published versions are listed at the top of the table of contents in the project sidebar and are visible to anyone who can view the project. Project members can also see unlisted versions. 

![Versions in Table of Contents](https://stoplight.io/api/v1/projects/cHJqOjI/images/rTN94UV29DY)

Editable versions are listed at the top of the Editor window. Users who can edit the project can see this list.

### Create a Version

1. Edit a Stoplight project.
2. From the **Versions** list, select **Create New Version**.

![versions-editable.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/O2zOHxVDWdo)

3. Provide a name for your version, and then select **Create**.

### "List" Versions

You can choose which versions should be visible to all viewers of a project. 

1. Open the **Project Settings** page. 
2. In the **Versions** area, set a version to **Listed**.
3. Select your primary project from the **Default Version** list.

![list-versions.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/leT6OXrsb8Y)


## Git Info and Branches

When a project is connected to Git, the **Git Info** setting shows which repository is being used and provides a link for cloning.

See [Branch Management](../2.-workspaces/h.branch-management.md) for more information on using Git with projects.

## Delete Projects

You can remove a project and all of its data from Stoplight. For Stoplight projects, the deletion is permanent. For Git projects, the underlying repo is not impacted, but the repo contents are removed from Stoplight.

To delete a project:

1. Edit a Stoplight project.
2. In the **Danger Zone** area, select **Remove Project**.
3. Type the project slug to confirm deletion.
4. Select **Remove Project**.

## Automation Settings

The **Automation** tab is available for projects connected to Git.

Use this tab to:

* **Install the Git Webhook**: The Git webhook keeps data in sync between Stoplight and the repository the project is connected to. If you chose not to install the Git webhook when you created the project, you can do so later. You can also re-install the webhook if you experience publishing issues.

* **Monitor Webhook Events**: View information about analyze events completed by the webhook. 

 See [Publish Git Projects](publishing-git-projects.md) and [Troubleshoot Git](../2.-workspaces/configure-git/f-troubleshoot-git.md) for more information.
