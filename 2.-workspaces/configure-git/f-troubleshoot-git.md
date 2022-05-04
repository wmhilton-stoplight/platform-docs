# Troubleshoot Git Connections

Use these troubleshooting steps to resolve errors related to your Git connections.

## Verify Integration Settings

1. Select **Settings** from the workspace home page, then navigate to the **Integrations** section.
2. Locate your Git integration (GitHub, GitLab, etc.), and verify that it is enabled.
3. Select the arrow to the right of the integration.
4. Verify that these settings match those in your Git provider:
   - Client ID and Client Secret
   - Host and API URL
   - Scopes and permission settings for your integration

See Stoplight requirements for each provider type:

- [Bitbucket Cloud](b.bitbucket-cloud.md)
- [Bitbucket Server](c.bitbucket-server.md)
- [GitHub Enterprise](d.github-enterprise.md)
- [GitLab](e.gitlab.md)

## Verify Firewall Settings 

If you are connected behind a firewall, verify that Stoplight's IP addresses are added to your allowlist. 

The fixed IP address is: **35.226.194.249**.

## Troubleshoot Webhooks

Webhooks are used to automatically sync data between Stoplight and your Git repository. If the Stoplight webhook is installed, use these steps when data is not synced or published to Stoplight from Git.

### Review in Stoplight

1. Log in to your workspace, and edit the project you are troubleshooting.
2. Select the **Project Settings** icon.
3. Select the **Automation** tab. (This tab is only visible for projects connected to a Git repository.)
4. Review listed webhooks events for errors or for events that appear to have failed.

### Track Branches

The default branch and all branches associated with a pull request will be automatically tracked for you. Tracking a Git branch will analyze it and add it to your list of published content in Stoplight. 

If documentation fails to automatically publish, use this feature to reanalyze the branch and publish your content.

To track Git branches that are not associated with a pull request, such as a development or version branch:

1. Log in to your workspace, and select the project you are troubleshooting.
2. Select the **Project Settings** icon.

![icon-git.PNG](https://stoplight.io/api/v1/projects/cHJqOjI/images/mvO9MmvbrgA)

<!--
focus: false
-->

![gear-icon.PNG](https://stoplight.io/api/v1/projects/cHJqOjI/images/s70YyGV5v4M)

3. Select the **Settings** tab.

![settings-git.PNG](https://stoplight.io/api/v1/projects/cHJqOjI/images/kvuQCCmXTO0)

4. Scroll down and select **+ Track Branch** from the **Branches** section.

![track-branch.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/V3sVYD69JIk)

<!-- theme: info -->
> **Note:** Tracking a Git branch will not create a new Git branch. It informs Stoplight to recognize webhooks with the branch name.

### Review in Git

Repository administrators can review recent webhook deliveries in your Git provider to see if there are errors or if events appear to have failed. For example, in GitHub, webhook settings and recent deliveries can be viewed on the **Webhooks** tab of the **Settings** page.

### Reinstall Webhooks

You can reinstall webhooks in Stoplight if you are unable to edit a Git project.

Reinstall the webhooks on the **Automation** tab for the project that you are having issues with.

## Can't find GitHub Organization 

This could be due to missing permissions in GitHub. Navigate to https://github.com/settings/applications and find the Stoplight app. Select it to go into the settings.

![GitHub Organization Access](../../assets/images/organization-access.png)

Notice the organization access at the bottom. Grant access to the organization you're looking to add repos from. You should then be able to add projects from your organization.

## Reclone Repository

To remove the local version of a branch and replace it with the server version: 

1. Log into your Studio Web workspace, then edit a project.
2. Ensure all changes are pushed to the Git server.
3. From the **Settings** menu, select **Reclone Project**.

## Reset Stoplight Access

If connection issues persist, revoke Stoplight authorization in your Git application, and then reauthorize.

## Remove Integration

Consider removing the integration from Stoplight, then confirming you can clone the Git repository using the HTTP/HTTPS URL to a location outside of Stoplight. 

To fully remove the integration from Stoplight:

1. Remove the integration from the Workspace Settings page. 
2. Disconnect the Git provider from your [**Account Settings** page](../q-account-settings.md). 



