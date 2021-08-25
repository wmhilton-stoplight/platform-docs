# Workspace Activity

> **Who can use this feature**
>
> - Available on the [Stoplight **Professional** plan](https://stoplight.io/pricing/), and above.
> - Only **Workspace owners and admins** can view member and guest activity

Activity logs provide a record of how members and guests are interacting with your workspace's resources.

## View activity logs

Workspace Owners and Admins are able to access activity logs in the **Activity** tab of the workspace's admin area.

1. From the Workspace home screen, click your workspace's name in the top left of the screen.
2. Click the **Activity** header at the top of the screen to open the activity logs.
3. Use the **Events** dropdown to select a specific type of event or view all of them.
4. Scroll down through the list to load older events.

![Workspace Activity](https://stoplight.io/api/v1/projects/cHJqOjI/images/1LU7lcRDa1U)

## Activity log events

Stoplight tracks the following information for every event:

- **Date** and **time** the event occured
- **IP address** of the user when the event occured
- **Member** who triggered the event

| Workspace Events         |                                                          |
| ------------------------ | -------------------------------------------------------- |
| **Membership changed**   | A member is added, removed or role is changed            |
| **Billing plan changed** | The billing plan is upgrade or downgraded                |
| **Integration changed**  | An integration is added, removed or settings are updated |
| **Workspace changed**    | The workspace slug is renamed                            |

| Group Events                      |                                               |
| --------------------------------- | --------------------------------------------- |
| **Created a group**               | A group is created                            |
| **Deleted a group**               | A group is deleted                            |
| **Renamed a group**               | A group is renamed                            |
| **Changed visibility of a group** | A group's visibility is changed               |
| **Membership changed**            | A member is added, removed or role is changed |

| Project Events                          |                                                                    |
| --------------------------------------- | ------------------------------------------------------------------ |
| **Created a project**                   | A project is created                                               |
| **Deleted a project**                   | A project is deleted                                               |
| **Renamed a project**                   | A project is renamed                                               |
| **Moved a project**                     | A project is moved to a different group or is removed from a group |
| **Updated contents of a project**                     | The project's contents were updated via Studio Web, CLI, or Webhook (worker) |
| **Changed visibility of a project**     | The project's visibility is changed                                |
| **Changed default branch of a project** | The project's default branch is changed                            |
| **Membership changed**                  | A member is added, removed or role is changed                      |
