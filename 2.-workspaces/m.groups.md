# Groups

Groups allow you to organize projects in your sidebar and grant project access to users in bulk.

<!-- theme: info -->
> This feature is available on the Stoplight **Professional** and **Enterprise** plans.

## Creating Groups

https://www.youtube.com/watch?v=d5e5Ac-6_U4


## Project Organization

Joining groups and their projects populates your sidebar. Making public groups with public projects adds the same helpful nested structure to your external docs too.

<!-- theme: success -->
> Discover [how to populate your sidebar](4.-documentation/Sidebar/a.customize-sidebar.md) and pin your favorite projects.

<!-- focus: center -->
![amazin_stop_small.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/9sSyrT8ZVYM)

## Moving Projects
There are a couple ways to move projects into a group:

**Option 1: Move a Project to a Group from the Projects List**

<!-- focus: top -->
![project_list_move_project.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/snuSLkPTcRQ 'From the menu in the Projects list')

**Option 2: Move a Project to a Group from the Project Settings**

<!-- 
focus: bottom 
bg: primary 
-->
![project_settings.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/gVH1Ilae6yE 'From the project settings page')


## Group Visibility & Access
Similar to [Project visibility](2.-workspaces/l.project-roles.md), Group visibility defines what account type(s) can see or join a group. It also impacts what kinds of projects can belong to that group.

**Public** groups, and any public projects in them, will be visible to everyone including logged out users. Use Public groups to organize your public-facing API documentation.

**Internal** groups can only be seen by workspace members. Workspace Guests cannot see this group unless they are added as a group member. Public projects are *not* allowed in internal groups so you can rest assured that nothing in an Internal Group will be publicly exposed.

## Group Member Roles

|                                 | Viewer | Editor | Admin | Owner |
|---------------------------------|--------|--------|-------|-------|
| Can invite members*              | ✅      | ✅      | ✅     | ✅     |
| Can add projects                |        | ✅      | ✅     | ✅     |
| Can view group settings         |        | ✅      | ✅     | ✅     |
| Remove members                  |        |        | ✅     | ✅     |
| Change group settings           |        |        | ✅     | ✅     |
| Change members role             |        |        | ✅     | ✅     |
| Change group visibility         |        |        | ✅     | ✅     |
| Remove projects                 |        |        | ✅     | ✅     |
| Transfer ownership of the group |        |        |       | ✅     |
| Delete the group                |        |        |       | ✅     |

> Note: Members can only invite members with their role or below. e.g. An Editor can invite a member as an editor or viewer. 

## Project Access for Group Members
Every member of a group will automatically have access to the *non-private* projects in that group. By default, a user's role in a group (e.g., Viewer, Editor) is **inherited** by the project.

However, project administrators can overwrite this default behavior to customize access for the group.

![Design_for__Project_Share_Dialog_Revamp_·_stoplightio_platform-internal.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/n81heWVncHo)

Learn more about how to [Manage Project Access](2.-workspaces/l.project-roles.md).




