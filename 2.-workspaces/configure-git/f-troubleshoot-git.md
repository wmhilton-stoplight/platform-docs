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

Webhooks are used to automatically sync data between Stoplight and your Git repository. Use these steps when data is not sycned or published to Stoplight from Git.

### Review in Stoplight

1. Log in to your workspace, and edit the project you are troublshooting.
2. Select the **Project Settings** icon.
3. Select the **Automation** tab. (This tab is only visible for projects connected to a Git repository.)
4. Review listed webhooks events for errors or for events that appear to have failed.

### Review in Git

Repository administrators can review recent webhook deliveries in your Git provider to see if there are errors or if events appear to have failed. For example, in GitHub, webhook settings and recent deliveries can be viewed on the **Webhooks** tab of the **Settings** page.

### Reinstall Webhooks

You can reinstall webhooks in Stoplight if you unable to resolve issues.

Reinstall the webhooks on the **Automation** tab for the project that you are having issues with.

## Reset Stoplight Access

If connection issues persist, revoke Stoplight authorization in your Git application, and then reauthorize.

## Remove Integration

Consider removing the integration from Stoplight, then confirming you can clone the Git repository  using the HTTP/HTTPS URL to location outside of Stoplight. 

To fully remove the integration from Stoplight:

1. Remove the integration from the Workspace Settings page. 
2. Disconnect the Git provider from your [**Account Settings** page](../q-account-settings.md). 



