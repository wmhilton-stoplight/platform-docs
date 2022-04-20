# Manage Group Access

Use a combination of visiblity type (public and internal) and roles to assign access to sets of projects organized in groups.

## Group Visibility & Access
Similar to [project visibility](l.project-roles.md), group visibility defines what account types can see or join a group. It also impacts what kinds of projects can belong to that group.

**Public** groups, and any public projects in them, are visible to everyone, including logged out users. Use public groups to organize your public-facing API documentation.

**Internal** groups can only be seen by workspace members. Workspace guests cannot see internal groups unless they are added as a group member. Public projects are *not* allowed in internal groups so you can rest assured that nothing in an internal group will be publicly exposed.

## Group Member Roles

|                                 | Viewer | Editor | Admin | Owner |
|---------------------------------|--------|--------|-------|-------|
| Can invite members*             | ✅    | ✅      | ✅     | ✅     |
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
Every member of a group automatically has access to the *non-private* projects in that group. By default, a user's role in a group (viewer, editor) is **inherited** by the project.

Guests have restricted access and can only view documentation in published branches. (Guests are automatically given restricted access when they are invited to a group or project.)

However, project administrators can override this default behavior to customize access for the group from the **Share Project** window. See [Project Access](l.project-roles.md#grant-project-permissions).

![project-access-for-group-members.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/RtI9C5YVrMU)

### Transfer Group Ownership

A group may have only one owner. To transfer ownership, select the new owner, and then change the role. Once confirmed, the former owner's role changes to Admin, and the selected member becomes the Owner.

To leave a group, an owner must transfer ownership to another group member.
