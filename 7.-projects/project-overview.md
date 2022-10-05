---
tags: [Projects]
---

# Project Overview

Within workspaces, projects are the most important concept in Stoplight. Projects help you design, store, and publish API descriptions, style guides, Markdown articles, and images. Most often, projects are created from source code repositories, such as Git.

Stoplight processes these assets in projects:

- API description documents in OpenAPI (versions 3.1, 3.0, and 2.0) and JSON Schema.
- Style guides
- Markdown articles
- Images (**JPEG,** **JPG**, **PNG** and **GIF** formats supported)

Different types of projects will contain different combinations. Here are a few ways projects might be used:

- **An open-source library:** JavaScript code and Markdown articles.
- **A REST API:** PHP source code, API Descriptions written in OpenAPI, and Markdown for "How To" instructions.
- **Community Contributed Documentation:** Markdown articles, with source code in another repository.

## Organize Projects

Before you add projects, consider how you want them organized and what they will contain.

First, answer these questions:

1. Who will own and administer the projects?
2. Should projects be visible to anyone or should access be limited to your organization?
3. How many APIs should be included in each project? Should you use a "monorepo" or a "multirepo" approach?
   - With a "monorepo" approach, you might have one project with a directory for each API. You can store the source code and API description inside that directory.
   - With a "multirepo" approach, you might have one project for each API. You can store the source code and API descriptions inside each project in any directory structure.

If you have many projects, you can [organize projects in groups](../2.-workspaces/m.groups.md). This feature is available on **Professional** and **Enterprise** plans.

## Add Projects

To add a project, log in to your workspace, and then:

* Select the **Add** icon (+) at the top of the left pane.
   OR
* Select the **Projects** tab on the workspace toolbar, and then select **New Project**.

For details, see [Add Projects](adding-projects.md).

## Manage Projects

### Projects List

Select the **Projects** tab on the **Workspace** toolbar to see the projects in your workspace.

![Projects List](../assets/images/projects-list.png)

1. All projects are shown in a list, with groups (Professional and Enterprise plans only) organized into collapsible folders.
2. Sort the list by name, owner, nodes (the number of items in a project), project type, the last edit of project or group settings, or visibility. 
3. Select a project or group to view more details. 

### Project Overview

Select a project from the list to see the **Overview** tab.

![Project Overview Page](../assets/images/projects-overview.png)

For API projects, you can:

* Select a [version or branch](project-settings.md).
* View the number of nodes by type (articles, models, APIs, and endpoints).
* For projects connected to Git, see the last commit for the selected branch. 
* See when project settings were last updated.

For API and Style Guide projects, you can:

* View the teams that have access to the project.
* Edit the [version or branch](project-settings.md). (This option isn't available for [Stoplight CLI projects](../2.-workspaces/f.working-with-local-projects.md).)
* Go to the published documentation for the project.
* Manage [project settings](project-settings.md).

### Members Overview

Select a project from the list, and then select the **Members** tab. 

<!-- focus: true -->
![project-members-tab.png](../assets/images/project-members-tab-2.png)

Here, you can:

* Invite members or teams to the project by user name, team name, or email address. You can set the role to the same or lower access as yours as you invite members.
* Set the [project visibility](../2.-workspaces/l.project-access.md#project-visibility) for API projects. (Style Guide projects always have internal visibility.)
* See the list of teams and members and change [project access](../2.-workspaces/l.project-access.md) to the same or lower access as yours. 
* Remove teams and members (project and workspace owners only).





