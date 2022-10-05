# Access Overview

Stoplight is an all-in-one platform that covers all integral parts of the API lifecycle including design, documentation, development, and governance. This requires different stakeholders from your organization to be on the platform.

Having all your collaborators on a single platform helps promote the **reusability** of artifacts across your organization, but you may need different levels of access for your stakeholders.

There are several components that Stoplight provides to control user access at different levels:

- Workspace Access
- Project Access
- Team Access
- Group Access

You can use different access levels to have fine-grained control on which users can access your Stoplight projects. You can also assign users different roles, to control the permissions a user has in the workspace and projects.

In addition to access level, there are also visibility controls that can affect what a user might be able to see in the platform:

- Group Visibility
- Project Visibility
- Article and API Visibility

Using visibility controls allows users to control which projects are visible to everyone (such as a public documentation portal), internally to all workspace users and guests, or private to a limited subset of users in your workspace. You can also control the visibility settings for articles and APIs, which can be especially useful when developing a public API with private or work-in-progress endpoints, for example.

And if you're using Stoplight with a Git integration, Git permissions can also affect what a user can access or edit in the platform.

Let's take a look at all the access and visibility options.

## Access Guidelines

### Workspace Access

Workspace-wide access is provided through roles:

- **Guest**: For external users to your organization that need limited access on a project-by-project basis.
- **Viewer**: For users that only need permission to view projects.
- **Maker**: For users that need permission to view and edit projects.
- **Billing Admin**: For users that need to manage account billing settings.
- **Admin**: For users that need to view, edit, and manage users, projects, and workspace settings.
- **Owner**: For users that need to view, edit, and manage users, projects, and workspace settings, as well as perform bulk actions. 

The **Guest** role is a special role that can be used to invite external members of your organization. Guests can only access projects that they have been added to. The other roles can be used to invite any members you would like to collaborate with while giving them easy access to the projects in your workspace.

Each role also has a different set of permissions. For more details, head to the [Workspace Roles](k.workspace-roles.md) page.

You can set the role when you [invite members](d.workspace-access.md) to your workspace.

### Project Access

While workspace roles define workspace-wide access, project access allows you to have granular control over who can manage, edit, or view a project.

User can have the following roles in a project:

- **Guest**: Can view the project and files that aren't marked as internal.
- **Viewer**: Can view the project in the documentation and design editor views.
- **Editor**: Can view and edit the project.
- **Admin**: Can view, edit, and manage the project and project settings.
- **Owner**: Can view, edit, and manage the project and project settings, as well as remove or transfer ownership of it.

Each role also has a different set of permissions. For more details, head to the [Manage Project Access](l.project-access.md) page.

### Team Access

<!-- theme: info -->
> Groups are available on the Stoplight **Professional** and **Enterprise** plans.

[Teams](teams.md) are a way to organize workspace members into teams, which allows users to more easily manage access to projects.

Similar to **project roles**, you can assign the following roles to a team in a project:

- Viewer
- Editor
- Admin

Users in a team can also have two roles:

- **Member**: Can access any projects the team has been added to.
- **Admin**: Can access any projects the team has been added to, as well as manage the team and team settings.

For more details about team access, head to the [Teams](teams.md) page.

### Group Access

<!-- theme: info -->
> Groups are available on the Stoplight **Professional** and **Enterprise** plans.

[Groups](m.groups.md) are a way to organize projects into folders, which allows users to more easily manage visibility settings for multiple projects, and organize the project sidebar.

Groups only have one specific role: **group admin**. A group admin can update the group visibility, manage group settings, and manage group admins.

For more details about group access, head to the [Manage Group Access](o.group-access.md) page.

## Visibility Guidelines

### Project Visibility

Project visibility determines who can view projects within or outside the organization. There are three options you can use:

- **Private (Starter plan and above)**: Only workspace members and guests with direct project access can view the project.
- **Internal**: All workspace members can view the project. Guests need direct access to view the project. New projects have internal visibility by default. 
- **Public**: Everyone including anonymous visitors can view the project.

For example, if you have a public API and would like to provide documentation for all your users, you can set your project visibility to **Public** and it'll be accessible by anyone with the workspace URL.

For more details about project visibility, head to the [Manage Project Access](l.project-access.md) page.

### Group Visibility

Similar to [project visibility](l.project-access.md), group visibility defines what account types can see or join a group. It also impacts what kinds of projects can belong to that group. There are two options for group visibility:

- **Public**: The group and any public projects in them are visible to everyone, including logged-out users. Use public groups to organize your public-facing API documentation.
- **Internal**: The group can only be seen by workspace members. Workspace guests can't see internal groups unless they're added as a group member. Public projects **aren't* allowed in internal groups so you can rest assured that nothing in an internal group will be publicly exposed.

For more details about group visibility, head to the [Manage Group Access](o.group-access.md) page.

### Article and API Visibility

Articles, APIs, and parts of an API description (paths and models) can be marked as internal to allow users to hide them from external and internal users with guest access.

This is useful for users that have public documentation, but also have internal documents, or APIs and endpoints, that are still being developed, or are only used internally, but live side-by-side with other public documentation or APIs. This allows users to manage public projects while still keeping any sensitive information private.

For more details about article and API visibility, head to the [Article and API visibility](../4.-documentation/set-internal-docs.md) page.

## Git Provider Permissions and Service Accounts

For users who integrate with Git providers, a user's permission in their Git provider can also have impact when accessing a project in Stoplight. Users who don't have edit permissions in a Git repository can't edit a Stoplight project connected to that repository.

The exception to that rule is if you're using service accounts. By connecting a service account to a Stoplight project, you can allow users who don't have a Git account, or don't have edit permissions in a repository, to use Stoplight to edit and make contributions to that project.

For more details about Git integrations, head to the [Git Overview](configure-git/a.configuring-git.md) page. And for more details about service accounts, head to the [Service Accounts](configure-git/h.service-accounts.md) page.
