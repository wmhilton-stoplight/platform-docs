# GitHub Enterprise

> This feature is available on the Stoplight **Pro** plan and above.

Use these steps to configure your GitHub Enterprise integration if you have a self-hosted deployment or need custom integration settings.

## GitHub Setup

1. In the upper-right corner of any page, select your profile photo, then select **Settings**.
2. In the left sidebar, select **Developer settings**.
3. Select  **OAuth Apps**.
4. Select **New OAuth App**.
> If you haven't created an app before, this button is labeled  **Register a new application**.
5. Add the following information:
   * **Application name**: Add the name of your app (e.g `Stoplight Integration`).
   * **Homepage URL**: Add the full URL to your app's website (e.g.: `https://stoplight.io`).
   * **Authorization callback URL**: Set as `https://stoplight.io/oauth/callback`.
6. Select **Register application**.
7. Select **Generate a new client secret**.

Read more about [creating a GitHub OAuth App](https://developer.github.com/apps/building-oauth-apps/creating-an-oauth-app/).

## Stoplight Setup

1. Select **Settings** from the workspace home page, then navigate to the **Integrations** section.
2. Select **Add** for GitHub.
3. Select **Customize integration settings**.
4. Add the following information:
   - **Host URL**: This is the URL where your instance of GitHub Enterprise is hosted.
   - **API URL**: This is the URL of the API of your instance of GitHub Enterprise. This is usually: `https://api.{HostURL}`.
   - **Client ID**: You can find this as `Client ID` under the OAuth Apps settings for the newly created app.
   - **Client Secret**: You can find this as `Client Secret` under the OAuth consumers settings for the newly created app.
   - **Redirect URL**: This URL should match the URL you used in the **Authorization callback URL** in your GitHub OAuth app settings.
5. Test your settings.
6. Select **Save**.

If successful, [add projects](../../7.-projects/adding-projects.md) to start working with projects from your GitHub Enterprise instance.

## Firewall and Fixed IP Address Configuration

All network traffic from Stoplight originates from a fixed IP address. This is done so that network administrators can allow Stoplight to access your internal Git or identity providers with minimal risk to your network.

If your self-hosted Git provider is behind a firewall, add Stoplight's fixed IP address **35.226.194.249** to your allowlist on port 443 over HTTPS.

## Troubleshooting

See [Troubleshoot Git](f-troubleshoot-git.md) for guidance on resolving connection issues. 
