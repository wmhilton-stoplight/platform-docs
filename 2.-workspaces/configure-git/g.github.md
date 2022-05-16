---
stoplight-id: dhre9np9qe1dc
---

# GitHub

GitHub is supported out of the box in Stoplight. To enable your workspace GitHub integration:

1. Select **Settings** from the workspace home page.
2. From the **Integrations** section, select **Add** next to GitHub.
3. Select **Use Default Configuration,** and then select **Save**.

In the setup dialog you can also:

- Enable/disable the integration
- Allow users to sign in and sign up by using GitHub

## Custom Configuration

> This feature is available on the Stoplight **Pro** plan and above.

By default, the GitHub integration will use Stoplight's OAuth application, but you can also customize your GitHub integration to use your own OAuth app.

### GitHub Setup

1. In the upper-right corner of any page, select your profile photo, then select **Settings**.
2. In the left sidebar, select **Developer settings**.
3. Select  **OAuth Apps**.
4. Select **New OAuth App**.
    - If you haven't created an app before, this button is labeled as **Register a new application**.
5. Add the following information:
   * **Application name**: Add the name of your app (e.g `Stoplight Integration`).
   * **Homepage URL**: Add the full URL to your app's website (e.g.: `https://stoplight.io`).
   * **Authorization callback URL**: We can get this value from Stoplight in the next steps, so for now use any URL such as `https://stoplight.io/oauth/callback`.
6. Select **Register application**.
7. Select **Generate a new client secret**.

Read more about [creating a GitHub OAuth App](https://developer.github.com/apps/building-oauth-apps/creating-an-oauth-app/).

### Stoplight Setup

1. Select **Settings** from the workspace home page, then navigate to the **Integrations** section.
2. Select **Add** for GitHub.
3. Select **Customize integration settings**.
4. Add the following information:
   - **Host URL**: Set as `https://github.com`.
   - **API URL**: Set as `https://api.github.com`.
   - **Client ID**: You can find this as `Client ID` under the OAuth Apps settings for the newly created app.
   - **Client Secret**: You can find this as `Client Secret` under the OAuth consumers settings for the newly created app.
   - **Redirect URL**: Copy this URL, and in your newly created GitHub OAuth app, paste it in the `Authorization callback URL` field and select **Update application**.
5. Test your settings.
6. Select **Save**.

If successful, [add projects](../../7.-projects/adding-projects.md) to start working with projects from your GitHub instance.

## Troubleshooting

See [Troubleshoot Git](f-troubleshoot-git.md) for guidance on resolving connection issues. 
