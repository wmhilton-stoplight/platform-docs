# Manage Group Access

[Group](m.groups.md) access and visibility can be managed by group admins and workspace owners.

## Group Access & Visibility

Similar to [project visibility](l.project-access.md), group visibility defines which users can see a group and its projects. It also impacts what kinds of projects can belong to that group.

- **Public** groups, and any public projects in them, are visible to everyone, including logged-out users. Use public groups to organize your public-facing API documentation.
- **Internal** groups can only be seen by workspace members. Workspace guests can't see internal groups unless they're added as a group member. Public projects **aren't* allowed in internal groups so you can rest assured that nothing in an internal group will be publicly exposed.

## Group Permissions

- Workspace owners and project owners:
  - Can move a project in and out of groups.
- Workspace owners and group admins:
  - Can add and remove group admins.
  - Can update group visibility.
  - Can manage group settings.
- Workspace owners:
  - Can delete groups.
