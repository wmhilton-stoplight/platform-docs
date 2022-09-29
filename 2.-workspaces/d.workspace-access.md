---
tags: [Workspaces]
stoplight-id: 490aa6725bcc4
---

# Manage Workspace Members

Once your workspace is set up, you can invite your colleagues and partners to collaborate on your API design.

There are two types of workspace users:

- **Members**: Roles can range from viewers to owners. Members are stakeholders in your organization. Depending on their role, members collaborate on API design, view documentation, and access mock servers. 
- **Guests**: Restricted to viewing documentation for projects they've been invited to. These users are people outside your company or organization, such as partners, who require authenticated access to the documentation.

Learn more about [Workspace Roles](k.workspace-roles.md).

>The number of workspace members and guests you can invite depends on your [Stoplight plan](https://stoplight.io/pricing/).

## Invite Members to Your Workspace 

1. From the workspace home page, select **Members**. 
2. On the **Member settings** page, select **Invite Members**. 
3. Enter one or more work **Email Addresses** of your teammates, select a **Role**, and then select **Send Invite**. 

![Add Members](../assets/images/invite-add-member.png)

Once sent, your invitations are set to pending and your team members are sent an email invitation. When they accept the request, they're added to your workspace. 

## Allow Access by Email Domain

> This feature is available on the [**Starter** plan](https://stoplight.io/pricing/) and above.

The fastest way to onboard your teammates is to configure an approved email domain and sending them a link to your workspace. This enables them to join your workspace without an invitation.

To configure an approved domain:

1. From the workspace home page, select **Settings**.
2. In the **Approved Domains** section, select **Add**.
3. Add your domain URL, and then select a default role for your domain users. 
3. Select **Save**.

You can configure one or more approved domains.

To change the default role or remove the domain, select the arrow to the right of the domain.

## Approve Join Requests

You must approve join requests when users want to join your workspace. If you allow access by email domain, you must approve join requests for users who register for your workspace with an email address that doesn't match your domain.

Join requests automatically expire and are deleted after 30 days.

Workspace owners and administrators are notified by email when users try to join their workspace. Select the link in the email to approve requests. You can also manually approve join requests from the **Members Settings** page.

1. From the workspace home page, select **Members**. 
2. Select members with a role of "pending."
3. Select the **Approve Request** check box.
4. Select the role for the users.
5. Select **Approve**.

![approve-requests.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/eUIWFYsOXOU)

## Manage Workspace Access

Since you will likely invite stakeholders from different parts of the API lifecycle, you can limit and restrict who gets access to what.

To change a member's role for your workspace:

1. From the workspace home page, select **Members**. 
2. Select the down arrow icon next to a user's role.
3. Select the new role from the drop-down menu.

If you're a workspace owner, you can also update multiple members at once:

1. From the workspace home page, select **Members**. 
2. Select one or more members by selecting the checkbox next to the user's name.
3. Select the **Change Role** icon.
4. Select the new role from the drop-down menu.
5. Select **Change** in the dialog box. 

### Change Guest Access 

Guests aren't considered members of your workspace, so their access is limited to viewing projects they're invited to. If the needs of your organization change, you can:

- **Upgrade guest access**: Change guests' roles to the Viewer role or above.
- **Downgrade to guest access**: Change members' roles to guest to restrict their access to only projects they've been invited to.

## Remove a Workspace Member

To remove a member from your workspace:

1. From the workspace home page, select **Members**.
2. Select the **ellipsis icon** (...) for the member you would like to delete, and select **Delete**.
3. Select **OK** in the dialog box.

If you're a workspace owner, you can also delete multiple members at once:

1. From the workspace home page, select **Members**. 
2. Select one or more members by selecting the checkbox next to the user's name.
3. Select the **Delete Member** icon.
4. Select **Delete** in the dialog box.
