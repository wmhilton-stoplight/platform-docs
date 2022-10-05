# Workspace Activity

> **Who can use this feature**
>
> - Available on the [Stoplight **Professional** plan](https://stoplight.io/pricing/), and above.
> - Only **Workspace owners and admins** can view member and guest activity

Activity logs provide a record of how members and guests are interacting with your workspace resources.

Stay up to date with all the changes happening within your Workspace. View and audit activity that has occurred across users, projects, teams, and groups in your workspace. 

When a project is updated, you can track who updated the project, from which branch, and where it was updated, whether from Studio, webhook, or pushed in via CLI. 

Filter by changes to membership and account types, project visibility, and creation or deletion of groups or projects leading to:

- Better governance of your API program.
- Increased security in your organization.
- Improved visibility across your workspace and members.

## View Activity Logs

Workspace Owners and Admins are able to access activity logs in the **Activity** tab of the workspace admin area.

1. From the Workspace home screen, select your workspace name in the top left of the screen.
2. Select the **Activity** header at the top of the screen to open the activity logs.
3. Use the **Events** dropdown to select a specific type of event or view all of them.
4. Scroll down through the list to load older events.

![Workspace Activity](https://stoplight.io/api/v1/projects/cHJqOjI/images/1LU7lcRDa1U)

## Activity Log Events

Stoplight tracks the following information for every event:

- **Date** and **time** the event occurred
- **IP address** of the user when the event occurred
- **Member** who triggered the event

| Workspace Events         |                                                          |
| ------------------------ | -------------------------------------------------------- |
| **Membership changed**   | A member is added, removed or role is changed            |
| **Billing plan changed** | The billing plan is upgraded or downgraded                |
| **Integration changed**  | An integration is added, removed or settings are updated |
| **Workspace changed**    | The workspace slug is renamed                            |

| Team Events             |                                       |
| ----------------------- | ------------------------------------- |
| **Created a team**      |  A team is created                    |
| **Delete a team**       | A team is deleted                     |
| **Renamed a team**      | A team is renamed                     |
| **Membership changed**  | A member is added, removed, or their role is updated |

| Group Events                      |                                               |
| --------------------------------- | --------------------------------------------- |
| **Created a group**               | A group is created                            |
| **Deleted a group**               | A group is deleted                            |
| **Renamed a group**               | A group is renamed                            |
| **Changed visibility of a group** | A group's visibility is changed               |
| **Membership changed**            | A member is added or removed |

| Project Events                          |                                                                    |
| --------------------------------------- | ------------------------------------------------------------------ |
| **Created a project**                   | A project is created                                               |
| **Deleted a project**                   | A project is deleted                                               |
| **Renamed a project**                   | A project is renamed                                               |
| **Moved a project**                     | A project is moved to a different group or is removed from a group |
| **Updated contents of a project**                     | The project's contents were updated via Studio Web, CLI, or Webhook (worker) |
| **Changed visibility of a project**     | The project's visibility is changed                                |
| **Changed default branch of a project** | The project's default branch is changed                            |
| **Membership changed**                  | A member is added, removed, or their role is changed                      |
| **Team membership changed**             | A team is added, removed, or their role is changed                      |


## Activity Logs FAQ

**How much data is retained?**

- No data is deleted; all data is currently retained.

**How far back does the log go?**

- August 18, 2021

**Can users change the length of time data is retained or the amount/types of data that are collected?**

- Not at this time.

**What users are tracked?**

- Internal and external: Stoplight can identify who is making the change and surface username, email address, and IP address. If someone outside of your workspace makes a change (via GitHub for example), you will be able to see their email address. 

