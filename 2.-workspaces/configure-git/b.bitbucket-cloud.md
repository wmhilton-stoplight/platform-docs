# Bitbucket Cloud

Use these steps to configure your Bitbucket Cloud integration if you have a self-hosted deployment or need custom integration settings.

## Bitbucket Cloud Setup

1. From your profile avatar in the bottom left, select the workspace in the **Recent Workspaces** list or select **All workspaces** to open an entire list.
2. Select **Settings** on the left sidebar to open the Workspace settings.
3. Select **OAuth consumers** under Apps and features on the left navigation, and then select **Add consumer**.
4. Add the following information:
    * **Name**: Give the consumer a name (e.g. **Stoplight Integration**).
    * **Callback URL**: Set as `https://stoplight.io/oauth/callback`.
    * **Mininum Permissions**: The miminum required  permissions for the consumer are:
       * Account - Read
       * Repositories - Admin
       * Repositories - Write
       * Pull requests - Read
       * Webhooks - Read and Write
5. Select **Save**.

![Bitbucket Cloud Settings](https://stoplight.io/api/v1/projects/cHJqOjI/images/xsUjXg0wGno)

Read more about [creating a BitBucket OAuth consumer](https://support.atlassian.com/bitbucket-cloud/docs/integrate-another-application-through-oauth/).

## Stoplight Setup

1. Select **Settings** from the workspace home page, then navigate to the **Integrations** section.
2. Select **Add** for Bitbucket Cloud.
3. Select **Customize integration settings**.
4. Add the following information:
   - **Host URL**: This is the URL where your instance of Bitbucket Cloud is hosted.
   - **API URL**: This is the URL of the API of your instance of Bitbucket Cloud. This is usually `api.{HostURL}/2.0`.
   - **Client ID**: You can find this as ***Key*** under the OAuth consumers settings for the newly created consumer.
   - **Client Secret**: You can find this as ***Secret*** under the OAuth consumers' settings for the newly created consumer.
5. Test your settings.
6. Select **Save**.

If successful, [add projects](../b.adding-projects.md) to start working with projects from your Bitbucket Cloud instance.

## Troubleshooting

See [Troubleshoot Git](f-troubleshoot-git.md) for guidance on resolving connection issues.