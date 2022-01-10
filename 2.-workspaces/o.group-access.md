# Manage Group Access

Use a combination of visiblity type (public and internal) and roles to assign bulk access to sets of projects.

## Group Visibility & Access
Similar to [project visibility](l.project-roles.md), group visibility defines what account types can see or join a group. It also impacts what kinds of projects can belong to that group.

**Public** groups, and any public projects in them, are visible to everyone, including logged out users. Use public groups to organize your public-facing API documentation.

**Internal** groups can only be seen by workspace members. Workspace guests cannot see this group unless they are added as a group member. Public projects are *not* allowed in internal groups so you can rest assured that nothing in an internal group will be publicly exposed.

## Group Member Roles

|                                 | Viewer | Editor | Admin | Owner |
|---------------------------------|--------|--------|-------|-------|
| Can invite members*              | ✅      | ✅      | ✅     | ✅     |
| Can add projects                |        | ✅      | ✅     | ✅     |
| Can view group settings         |        | ✅      | ✅     | ✅     |
| Remove members                  |        |        | ✅     | ✅     |
| Change group settings           |        |        | ✅     | ✅     |
| Change member roles             |        |        | ✅     | ✅     |
| Change group visibility         |        |        | ✅     | ✅     |
| Remove projects                 |        |        | ✅     | ✅     |
| Move projects in and out of groups |     |        |       | ✅     |
| Transfer ownership of the group |        |        |       | ✅     |
| Delete the group                |        |        |       | ✅     |

> *Members can only invite members with their role or below. For example, an editor can invite a member as an editor or viewer. 

## Project Access for Group Members
Every member of a group will automatically have access to the *non-private* projects in that group. By default, a user's role in a group (viewer, editor) is **inherited** by the project.

Guests have restricted access and can only view documentation in published branches. (Guests are automatically given restricted access when they are invited to a group or project.)

However, project administrators can overwrite this default behavior to customize access for the group from the **Share Project** window. See [Project Access](l.project-roles.md#grant-project-permissions)

![project-access-for-group-members.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/RtI9C5YVrMU)

Learn more about how to [Manage Project Access](l.project-roles.md).

