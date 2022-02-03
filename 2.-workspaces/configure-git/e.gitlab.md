# GitLab

> This feature is available on the Stoplight **Pro** plan and above.

Use these steps to configure your GitLab integration if you have a self-hosted deployment or need custom integration settings.

## GitLab Setup

1. Verify that [HTTP/HTTPS access is enabled](https://docs.gitlab.com/ee/user/admin_area/settings/visibility_and_access_controls.html#configure-enabled-git-access-protocols) in Gitlab.
2. Navigate to **Profile Settings > Edit Profile> Applications** to add a new application via your profile.
3. Add the following information on the **New Application** form:
   * **Name**: Enter a Name (e.g `Stoplight Integration`).
   * **Redirect URI**: Set as `https://stoplight.io/oauth/callback`.
   * **Expire access token**: Clear this checkbox.
   * **Scopes**: Select `api`.
4. Select **Save application**.

![GitLab Setup](https://stoplight.io/api/v1/projects/cHJqOjI/images/vAVNMM9zwOg)

Read more about [creating a GitLab OAuth App](https://docs.gitlab.com/ee/integration/oauth_provider.html#adding-an-application-through-the-profile).

## Stoplight Setup

1. Select **Settings** from the workspace home page, then navigate to the **Integrations** section.
2. Select **Add** for GitLab.
3. Select **Customize integration settings**, and then add the following information:
   - **Host URL**: This is the URL where your instance of GitLab is hosted.
   - **API URL**: This is the URL of the API of your instance of GitLab. This is usually: `{HostURL}/api/v4`.
   - **Client ID:** This is `Application ID` under the application settings for the app you created in GitLab.
   - **Client Secret**: You can find this as `Secret` under the application settings for the newly created app.
4. Test your settings.
5. Select **Save**.

If successful, [add projects](../b.adding-projects.md) to start working with projects from your GitLab instance.

## Troubleshooting

See [Troubleshoot Git](f-troubleshoot-git.md) for guidance on resolving connection issues.