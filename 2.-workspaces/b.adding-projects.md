---
tags: [Workspaces]
---

# Add Projects

Within workspaces, project are the most important concept in Stoplight. Projects help you design, store, and publish API descriptions, style guides, Markdown articles, and images. Most often, projects are created from source code repositories, such as Git. 

Stoplight processes these assets in projects: 

- API description documents in OpenAPI (versions 3.1, 3.0, and 2.0) and JSON Schema.
- Style guides 
- Markdown articles
- Images

Different types of projects will contain different combinations. Here are a few ways projects might be used:

- **An open-source library:** JavaScript code and Markdown articles.
- **A REST API:** PHP source code, API Descriptions written in OpenAPI, and Markdown for "How To" instructions.
- **Community Contributed Documentation:** Markdown articles, with source code in another repository.

## Organize Projects

Before you add projects, consider how you want them organized and what they will contain. 

First, answer these questions:

1. Who will own and administer the projects?
2. Should our projects be visible to anyone or should access be limited to our organization? 
3. How many APIs go should we include in each project? Should you use "monorepo" or a "multirepo" approach?
   - With a "monorepo" approach, you might have one project with a directory for each API. You can store the source code and API description inside that directory.
   - With a "multirepo" approach, you might have one project for each API. You can store the source code and API descriptions inside each project in any directory structure.

If you have a large number of projects, you can [organize projects in groups](m.groups.md). This feature is available on **Professional** and **Enterprise** plans.

## Project Types

There are three types of projects you can add to your workspace:

- Stoplight projects 
- Git projects
- CLI projects

## Add Stoplight Projects

Stoplight projects offer realtime collaboration. Data is stored in Stoplight. A Git connection is not required and there is no extra setup. You can:

  - Create a blank project
  - Import an existing OpenAPI file

  ![add-projects](../assets/images/add-stoplight-project.png)

### Add a Blank Project

1. Log in to your workspace, and then select the **Add** icon (+) at the top of the left pane.
2. From the **Add a Project** page, select **Create Blank Project**.
3. Provide a name for your project, and then set the [project visibility](l.project-roles.md). 
4. Select **Create Project**.
5. Select **Edit** to design your API with [Stoplight Studio](../3.-design/a.overview.md).

### Import an OpenAPI File

1. Log in to your workspace, and then select the **Add** icon (+) at the top of the left pane.
2. From the **Add a Project** page, select **Import OpenAPI File**.
3. Provide a name for your project, and then set the [project visibility](l.project-roles.md). 
4. Select **Create Project & Import File**.
5. Select the OpenAPI file to import, and then select **Import**.
6. Use [Stoplight Studio](../3.-design/a.overview.md) to update the API.

## Add Projects from Git

The quickest and recommended way to get projects into Stoplight is to pull them in from Git. Git projects offer asynchronous push/pull collaboration across multiple branches. Data is stored in Git, but there is not extra setup. You can:

  - Create a blank project
  - Add a project from Bitbucket Cloud
  - Add a project from GitHub
  - Add a project from GitLab

![add-projects](../assets/images/add-git-project.png)

> Stoplight works with many popular Git providers. Read more about [configuring Git](configure-git/a.configuring-git.md).

To add projects from Git:

1. Log in to your workspace, and then select the **Add** icon (+) at the top of the left pane.
2. Select an option under **Git Project**.
3. Select  **Connect**. Follow the instructions on the popup screen to authorize.
4. Upon successful authentication, choose your organization, and then select the repositories you want to import.
5. Next, select **Add Git Project**.

Once the project is created and the anaylzer has completed, it will contain Markdown articles and API descriptions that are stored in the Git repository. Use [Stoplight Studio](../3.-design/a.overview.md) to modify these files.

### Custom Git Configurations

If your Git provider isn't listed or you're using a custom configuration, see [Custom Configuration for Git](#custom-configuration-for-git). 

## Add CLI Projects

If you use a version control system other than Git (Mercurial, SVN, SourceSafe, Bazaar), use the Stoplight CLI to add a a local project. 

 ![add-projects](../assets/images/add-cli-project.png)

Stoplight CLI is a command-line tool, available as [an NPM module](https://www.npmjs.com/package/@stoplight/cli), that can publish changes to Stoplight. CLI projects are shown in Explorer like other projects. They won't be editable in Studio Web, but the content will be available to read and search like anything else. 

Read more about [working with local projects](f.working-with-local-projects.md).

## Share Projects

For external users, share your workspace URL with users to let them access your documentation. For internal or private projects, [invite users](../2.-workspaces/d.inviting-your-team.md) to the workspace directly. 

