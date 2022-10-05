# Workspace Roles

Workspace roles are predefined according to varying access needs. You can assign roles to members when you invite them to your workspace. 

> **Note**: Roles apply to authenticated users. Documentation is always visible for public projects that don't require users to log in.

Roles include: 

- **Guest**: Restricted to viewing documentation for projects that they're granted explicit access to, except for articles, APIs, API paths, and models marked as internal. Guests are users outside your company or organization, such as partners who require authenticated access to the documentation. 
- **Viewer**: Can view documentation and consume mock servers. Viewers are usually developers and other stakeholders inside the organization consuming the API but don't need to make changes to API design and docs. Viewers can view **published branches** of all internal projects and **all branches** of projects they're granted direct access to. [Learn how to add members to a project](l.project-access.md).
- **Maker**: In addition to viewer access, can create projects, and edit all internal Git projects and projects they're granted direct access to. Makers are usually product managers, technical writers, and architects who are creating and editing API designs and docs.
- **Owner, Admin, and Billing**: In addition to maker access, can manage members, billing, and make changes to the workspace, such as adding landing page content and setting themes. You can have multiple owners for a workspace.

## Permissions Legend

 Permission         | Guest | Viewer | Maker | Billing | Admin | Owner |
|---------------------------|-------|-------|--------|--------|--------|--------|
| Can be granted project read access | ✅ | ✅ | ✅ | ✅ | ✅ | ✅
| Can be granted project write access |     |  | ✅ | ✅ | ✅ | ✅ |
| Browse all internal projects       |     | ✅ | ✅ | ✅ | ✅ | ✅ |
| View members                 |     | ✅ | ✅ | ✅ | ✅ | ✅ |
| Add new API projects         |     |     | ✅ | ✅ | ✅ | ✅ |
| Add new style guide projects |     |     |    |    | ✅ | ✅ |
| Set default style guides     |     |     |    |    | ✅ | ✅ |
| Can use Studio               |     |     | ✅ | ✅ | ✅ | ✅ |
| Manage project groups        |     |     |    | ✅ | ✅ | ✅ |
| Manage billing               |     |     |    | ✅ | ✅ | ✅ |
| Manage members               |     |     |    | ✅ | ✅ | ✅ |
| Manage workspace             |     |     |    | ✅ | ✅ | ✅ |
| Manage all projects               |     |     |  |  |  | ✅ |
| Perform bulk actions         |     |     |    |     |    | ✅ | 
| Delete workspace             |     |     |    |     |    | ✅ |   

## What's Next?

Once you understand workspace roles, you can: 

1. [**Invite Team Members**](d.workspace-access.md)
2. [**Manage Project Access**](l.project-access.md)