# GitHub Enterprise

> This feature is available on the Stoplight **Pro** plan and above.

Configure your GitHub Enterprise integration by following these instructions.

## GitHub Setup

1. In the upper-right corner of any page, select your profile photo, then select **Settings**.
2. In the left sidebar, select **Developer settings**.
3. Select  **OAuth Apps**.
3. Select **New OAuth App**.
> If you haven't created an app before, this button is labeled  **Register a new application**.
4. Add the following information:
   * **Application name**: Add the name of your app (e.g `Stoplight Integration`).
   * **Homepage URL**: Add the full URL to your app's website (e.g.: `https://stoplight.io`).
   * **Authorization callback URL**: Set as `https://stoplight.io/oauth/callback`.
5. Select **Register application**.

Read more about [creating a GitHub OAuth App](https://developer.github.com/apps/building-oauth-apps/creating-an-oauth-app/).

## Stoplight Setup

1. Select **Settings** from the workspace home page, then navigate to the **Integrations** section.
2. Select **Add** for GitHub.
3. Select **Customize integration settings**.
4. Add the following information:
   - **Host URL**: This is the URL where your instance of GitHub Enterprise is hosted.
   - **API URL**: This is the URL of the API of your instance of GitHub Enterprise. This is usually: `api.{HostURL}`.
   - **Client ID**: You can find this as `Client ID` under the OAuth Apps settings for the newly created app.
   - **Client Secret**: You can find this as `Client Secret` under the OAuth consumers settings for the newly created app.
   - **Redirect URL**: Copy this URL and add it to your GitLab OAuth application.
5. Test your settings.
6. Select **Save**.

If successful, [add projects](../b.adding-projects.md) to start working with projects from your GitHub Enterprise instance.

## Troubleshooting

See [Troubleshoot Git](f-troubleshoot-git.md) for guidance on resolving connection issues. 
