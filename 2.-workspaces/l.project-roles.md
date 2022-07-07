# Manage Project Access

While workspace roles define workspace-wide access, not all projects need to be accessible or editable by everybody in the workspace. 

Visibility and permission settings within projects allow granular control over who can do what. Users will see different projects depending on the following criteria:

- Their permissions in the **workspace**. See [Workspace Roles](k.workspace-roles.md).  
- The **visibility settings** of the project (private, public, or internal).
- Their role in the **project**. 

Use one of these methods to manage project access:

* Select the **Share** button when you are editing a project or from the project sidebar when you are viewing a project.
<!-- focus: false -->
![Share a project](https://stoplight.io/api/v1/projects/cHJqOjI/images/wiaJr2Ql6FI)

* Select the **Projects** tab on the **Workspace** toolbar. Select a project, and then select the [**Members** tab](../7.-projects/project-settings.md#members-overview) on the **Project** details pane.

From here, you can:

- Invite users to the project by name or email address.
- Set the project visibility.
- Set the role for each project member.
- Change project ownership.
- Remove members.

## Invite Users

You can add existing workspace members by their user name or invite new members and guests by email.

Project members, except guests, can add members to the project with their role or lower. For example, a project editor can add a new member with either the Editor role or Viewer role, but not with the Admin or Owner role.

## Change Project Visibility

Project visibility determines who can view projects within or outside the workspace. 

**Private (Starter plan and above)**: Only workspace members and guests with direct project access can view the project.

**Internal**: All workspace members can view the project. Guests need direct access to the project. New projects have internal visibility by default. 

**Public**: Everyone including anonymous visitors can view the project.

> Style guide projects can only be set to internal visibility. 

## Project Roles

Project roles determine the level of access for each project member. To change a user's role for a project, open the **Share** dialog, locate the user, then change the role. 

**Guest**: Can view documentation in published branches once they've been invited, except for articles, API paths, and models marked as internal. You cannot assign the guest role; it is automatically assigned when guests are invited to a project.

**Viewer**: Can view documentation, access mock servers for published and unpublished branches, and invite users. 

**Editor**: Can edit the project in Studio and track new branches.

**Admin**: Can edit project settings, manage member role, and remove members.

**Owner**: Can remove the project and transfer ownership to another member. There can only be one owner per project.

Permissions for each project role:

| Permission                | Owner | Admin | Editor | Viewer | Guest (Restricted) |
|---------------------------|-------|-------|--------|--------|--------|
| View listed branches      | ✅     | ✅    | ✅      | ✅      | ✅    |
| View internal items       | ✅     | ✅    | ✅      | ✅      |      |
| View unlisted branches    | ✅     | ✅    | ✅      | ✅      |       |
| Access mock servers       | ✅     | ✅    | ✅      | ✅      |       |
| Add members               | ✅     | ✅    | ✅      | ✅      |       |
| Edit in Studio            | ✅     | ✅    | ✅      |        |       |
| Drag-and-drop images      | ✅     | ✅    | ✅      |        |       |
| Track branches            | ✅     | ✅    | ✅      |        |       |
| View settings             | ✅     | ✅    | ✅      |        |       |
| Enable style guides       | ✅     | ✅    | ✅      |        |       |
| Disable default style guides*| ✅ | ✅ |  ✅  |      |        |       |
| Edit settings             | ✅     | ✅    |        |        |        |
| Manage service accounts   | ✅     | ✅    |        |        |        |
| Remove members            | ✅     | ✅    |        |        |        |
| Remove project            | ✅     |       |        |        |       |
| Transfer ownership        | ✅     |       |        |        |       |
| Leave the project         |        | ✅    | ✅      | ✅      |✅    |

> **Note:** To edit Git projects, users need permissions in both Stoplight and the Git repository.

`*` Unless disabled at the workspace level. See [Governance Settings](workspace-governance.md) for details.

### Request Project Permissions

If you need access to a project, the project's owner can add you as a member or upgrade your role. To find out who is the project owner, hover over their avatar in the projects list.

![Find Project Owner](https://stoplight.io/api/v1/projects/cHJqOjI/images/YdQNNaKkjIU)

### Transfer Project Ownership

A project may have only one owner. To transfer ownership, select the new owner, and then change the role. Once confirmed, the former owner's role changes to Admin and the selected member becomes the Owner.

<!--
focus: false
-->
![](../assets/images/transfer-project-ownership.png)

To leave a project, an owner must transfer ownership to another project member.

### Remove a Project Owner

When removing members from the workspace or downgrading members to guests, you will automatically take ownership of all projects they currently own. You can then transfer ownership of those projects to another member.

### Remove Project Members

To remove a member from a project, select the member, and then select **Remove Member**.