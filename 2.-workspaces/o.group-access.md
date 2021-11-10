# Manage Group Access

Use a combination of visiblity type (public and internal) and roles to assign bulk access to sets of projects.

## Group Visibility & Access
Similar to [Project visibility](l.project-roles.md), Group visibility defines what account type(s) can see or join a group. It also impacts what kinds of projects can belong to that group.

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

However, project administrators can overwrite this default behavior to customize access for the group from the Share Project window.

![project-access-for-group-members.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/RtI9C5YVrMU)

Learn more about how to [Manage Project Access](l.project-roles.md).

