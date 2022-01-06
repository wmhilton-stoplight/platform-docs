# Publish Git Projects

Webhooks are HTTP requests triggered by one server to let another server know something has changed. Most Git providers offer these to let integrated applications like Stoplight know about new commits, pull requests, and more.

Webhooks are set up automatically on Stoplight projects for workspaces that are connected with the default Stoplight Git integrations. 

When changes are pushed to any branch, the Git server receives the push and sends a webhook to Stoplight. If the [branch has publishing enabled](../2.-workspaces/h.branch-management.md), automatic updates are made to documentation, mock servers, explorer, etc. This usually occurs within a few seconds after each push.

If you have [connected Git providers](../2.-workspaces/configure-git/a.configuring-git.md) with your own hosted Git servers or your own credentials, you will need to set up webhooks.

## Work with Webhooks

To view incoming and completed webhook events:

1. Open a Git project in your workspace. 
2. Select the **Project Settings** icon. 
3. Select the **Automation** tab. 

![The Webhook Events header on the automation tab showing history of two recent "events", both completed quickly and successfully.](../assets/images/webhook-events.png)

## Troubleshoot Webhooks

If changes are not publishing, use our [Troubleshooting](../c.troubleshooting.md) steps to review webhook events to debug the problem. 