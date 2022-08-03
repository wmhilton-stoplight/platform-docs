---
stoplight-id: r5nqj5dw2cdxn
---

# Azure DevOps Server

> This feature is available on the Stoplight **Pro** plan and above.

The versions Stoplight supports for Azure DevOps Server are:

- TFS 2018 Update 2
- TFS 2018 Update 3

Use these steps to configure your Azure DevOps Server integration.

## Azure DevOps Server Setup

There are two things you'll need from Azure:

1. The URL of your instance of Azure DevOps Server. The format should be: `https://{your_server_ip:port}/tfs/{your_collection_name}`.
2. A **personal access token**. To generate a personal access token:
    1. In the upper-right corner of the page, select your profile photo, then select **Security** or **Personal access tokens** depending on your version of Azure DevOps Server.
    2. Select **Add** or **New Token**.
    3. Add a name in the **Description** field, set the expiration time, and select **All Scopes** for the **Authorized Scopes** field. 
    4. Select **Create**.
    5. Save your newly generated token for use in the next steps.
    
You can find more details about [creating a personal access token in Azure DevOps Server here](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=Windows).

## Stoplight Setup

1. Select **Settings** from the workspace home page, then navigate to the **Integrations** section.
2. Select **Add** for Azure DevOps Server.
4. Add the following information:
    - **Name**: Add a name for the integration
    - **Collection URL**: Add the Collection URL of your instance. The format should be: `https://{your_server_ip:port}/tfs/{your_collection_name}`
5. Test your settings.
6. Select **Save**.

You can now connect an Azure DevOps Server account to your Stoplight account by going to:

- **Add Project**, selecting **Add from Azure DevOps Server**, and selecting **Connect Azure DevOps Server**.

Or by going to:

- **Account Settings**, selecting the **Connected Accounts** tab, and selecting **Connect** next to the Azure DevOps Server logo.

Whichever path you choose, a popup dialog for **Azure DevOps Server authentication** will be displayed where you can input a **Username**, and **Personal Access Token** (which you created in the previous steps).

> Remember to use a personal access token, and not a password, to connect a new Azure DevOps Server account.

## Firewall and Fixed IP Address Configuration

All network traffic from Stoplight originates from a fixed IP address. This is done so that network administrators can allow Stoplight to access your internal Git or identity providers with minimal risk to your network.

If your self-hosted Git provider is behind a firewall, add Stoplight's fixed IP address **35.226.194.249** to your allowlist on port 443 over HTTPS.

## Troubleshooting

See [Troubleshoot Git](f-troubleshoot-git.md) for guidance on resolving connection issues. 
