---
stoplight-id: e6abea900af9f
---

# Azure DevOps Services

> For the Azure DevOps Services integration to work, your Azure DevOps organization settings must have "**Third-party application access via OAuth**" enabled. You can find more details about that setting [here](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/change-application-access-policies?view=azure-devops).

Azure DevOps Services is supported out of the box in Stoplight. To enable your workspace Azure DevOps Services integration:

1. Select **Settings** from the workspace home page.
2. From the **Integrations** section, select **Add** next to Azure DevOps Services.
3. Select **Use Default Configuration,** and then select **Save**.

In the setup dialog you can also:

- Enable/disable the integration
- Allow users to sign in and sign up by using Azure DevOps Services

Azure DevOps organizes repositories inside of [projects](https://docs.microsoft.com/en-us/azure/devops/organizations/projects/about-projects?view=azure-devops), so each Azure DevOps project can contain multiple Git repositories. This is different from Stoplight projects, where each project represents a single Git repository or a Stoplight Web project.

## Custom Configuration

> This feature is available on the Stoplight **Pro** plan and above.

By default, the Azure DevOps Services integration will use Stoplight's OAuth application, but you can customize your Azure DevOps Services integration to use your own OAuth 2.0 app.

### Azure DevOps Services Setup

1. Go to `https://app.vsaex.visualstudio.com/app/register` to register your app.
2. Add the following information:
   * **Company name**: Set as `Stoplight`.
   * **Application name**: Add the name of your app (for example, `Stoplight Integration`).
   * **Application website**: Set as `https://stoplight.io`.
   * **Authorization callback URL**: You can get this value from Stoplight in the next steps, so for now use any URL such as `https://stoplight.io/oauth/callback`.
   * **Authorized scopes**: Select the following scopes:
     * Code (read, write, and manage)
     * Project and team (read)
3. Select **Create Application**.

Read more about [creating an Azure DevOps Services OAuth 2.0 App](https://docs.microsoft.com/en-us/azure/devops/integrate/get-started/authentication/oauth?toc=%2Fazure%2Fdevops%2Forganizations%2Ftoc.json&bc=%2Fazure%2Fdevops%2Forganizations%2Fbreadcrumb%2Ftoc.json&view=azure-devops).

### Stoplight Setup

1. Select **Settings** from the workspace home page, then navigate to the **Integrations** section.
2. Select **Add** for Azure DevOps Services.
3. Select **Customize integration settings**.
4. Add the following information:
   - **Host URL**: Set as `https://azure.com`.
   - **API URL**: Set as `https://dev.azure.com`.
   - **Client ID**: You can find this as `App ID` under the Application Settings for the newly created app.
   - **Client Secret**: You can find this as `Client Secret` under the Application settings for the newly created app.
   - **Redirect URL**: Copy this URL, and in your newly created Azure DevOps Services OAuth app, paste it in the `Authorization callback URL` field and select **Update application**.
5. Test your settings.
6. Select **Save**.

If successful, [add projects](../../7.-projects/adding-projects.md) to start working with projects from your Azure DevOps Services instance.

## Troubleshooting

See [Troubleshoot Git](f-troubleshoot-git.md) for guidance on resolving connection issues.