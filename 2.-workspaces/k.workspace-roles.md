# Workspace Roles

Workspace roles are predefined according to varying access needs. You can assign roles to members once they've been invited to your workspace. 

> **Note**: Roles apply to authenticated users. Documentation is always visible for public projects that do not require users to log in.

Roles include: 

**Guests**: Restricted to viewing documentation for projects that they are granted explicit access to. Guests are users outside your company or organization, such as partners who require authenticated access to the documentation. 

**Viewer**: Can view documentation and consume mock servers. Viewers are usually developers and other stakeholders inside the organization consuming the API but don't need to make changes to API design and docs. Viewers can view **published branches** of all internal projects and **all branches** of projects they are granted direct access to. [Learn how to add members to a project](l.project-roles.md).

**Maker**: In addition to viewer access, can create projects, edit all internal Git projects and projects they are granted direct access to. Makers are usually product managers, technical writers, and architects who are creating and editing API designs and docs.

**Owners, Admins and Billing**: In addition to maker access, can manage team members, billing, and make changes to the workspace, such as adding landing page content and setting themes.

## Permissions Legend

 Permission         | Guest | Viewer | Maker | Billing | Admin | Owner |
|---------------------------|-------|-------|--------|--------|--------|--------|
| Can be granted direct access | ✅ | ✅ | ✅ | ✅ | ✅ | ✅
| View internal projects       |     | ✅ | ✅ | ✅ | ✅ | ✅ |
| View members                 |     | ✅ | ✅ | ✅ | ✅ | ✅ |
| Add new projects             |     |     | ✅ | ✅ | ✅ | ✅ |
| Can use Studio               |     |     | ✅ | ✅ | ✅ | ✅ |
| Manage project groups        |     |     |    | ✅ | ✅ | ✅ |
| Manage billing               |     |     |    | ✅ | ✅ | ✅ |
| Manage members               |     |     |    | ✅ | ✅ | ✅ |
| Manage workspace             |     |     |    | ✅ | ✅ | ✅ |
| Perform bulk actions         |     |     |    |     |    | ✅ |  

## What's Next?

Once you understand workspace roles, you can: 

1. [**Invite Team Members**](d.inviting-your-team.md)
2. [**Manage Project Access**](l.project-roles.md)