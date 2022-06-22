---
stoplight-id: 10d5c35b280a9
---

# Service Accounts Overview

<!--
focus: false
-->
![New feature badge](../../assets/images/badge-new-small.png)

> This feature is available for all Stoplight plans, but Stoplight highly recommends it for large teams and organizations.

Service Accounts are a special type of account, generally representing a non-user, that teams or organizations can use to manage authentication and permissions with third-party services.

Creating a service account in your Git provider and using that in Stoplight can help:

- Ensure that the connection between your team’s repositories and Stoplight isn't tied to an individual user account
- Prevent any sync issues in case a user is removed from your organization by accident or leaves your organization
- Allow users without Git accounts to contribute to projects in Stoplight
- Limit the scope of access and reduce security risks for IT admins

Once you configure a service account in your Stoplight project, **any Git operations will be done using the service account credentials**. Besides the benefits listed above, this shouldn't have any impact on the user's ability to clone, edit, or publish changes to Git projects in Stoplight.

The main difference that users will see is in their Git commit messages, which will use the service account for the commit operation, and the Stoplight user as the author of the commit. The commit message will also be modified to include details about the service account. For example, this is what a commit will look like on GitHub:

![Example of a commit on GitHub after a service account is connected to Stoplight. The commit message includes the user name and appended to it says "on behalf of service-account." The author section also includes both the username and the service account username in the format "user authored and service-account-username committed 3 minutes ago"](../../assets/images/service-accounts-commit-message-2.png)

Currently, Stoplight supports:

- GitHub
- GitLab
- Bitbucket Cloud
- Bitbucket Server
- Azure DevOps Server

## Create a Service Account in Your Git Provider

The first step for using a Service Account in Stoplight is creating a service account in your Git provider. For each provider, we recommend following their documentation on how to create a new account.

### GitHub

1. [Create a new account in GitHub](https://docs.github.com/en/get-started/signing-up-for-github/signing-up-for-a-new-github-account).
2. For users who have their GitHub accounts integrated with a SAML provider, make sure that you talk to your IT admin so that you can either:
   - Create a new user in your SAML provider to be used as a service account.
   - Manage the settings for enforcing SAML authentication so you can log in with your service account.
   - You can find more details about this in the [GitHub documentation](https://docs.github.com/en/enterprise-cloud@latest/organizations/granting-access-to-your-organization-with-saml-single-sign-on/managing-bots-and-service-accounts-with-saml-single-sign-on).
3. [Add your account to your organization](https://docs.github.com/en/organizations/managing-membership-in-your-organization/inviting-users-to-join-your-organization).
4. Make sure the [account has read/write access](https://docs.github.com/en/organizations/managing-access-to-your-organizations-repositories) to the repositories you want to use in Stoplight.

### GitLab

1. [Create a new account in GitLab SaaS](https://gitlab.com/users/sign_up) or in your [organization's instance of GitLab](https://docs.gitlab.com/ee/user/profile/account/create_accounts.html).
2. For users who have their GitLab accounts integrated with a SAML provider, make sure that you talk to your IT admin so that you can either:
   - Create a new user in your SAML provider to be used as a service account.
   - Manage the settings for enforcing SAML authentication so you can log in with your service account.
   - You can find more details about this in the [GitLab documentation](https://docs.gitlab.com/ee/user/group/saml_sso/).
3. Make sure the [account has read/write access](https://docs.gitlab.com/ee/user/project/members/) to the repositories you want to use in Stoplight.

### Bitbucket Cloud

1. [Create a new account in Bitbucket Cloud](https://id.atlassian.com/signup?application=bitbucket\&continue=https%3A%2F%2Fbitbucket.org%2Faccount%2Fsignin%2F%3Fnext%3D%252F).
2. For users who have their Bitbucket Cloud accounts integrated with a SAML provider, make sure that you talk to your IT admin so that you can create a new user in your SAML provider to be used as a service account.
3. [Add your account to your workspace](https://support.atlassian.com/bitbucket-cloud/docs/grant-access-to-a-workspace/).
4. Make sure the account has read/write access to the repositories you want to use in Stoplight.

### Bitbucket Server

1. [Create a new account in your Bitbucket Server instance](https://confluence.atlassian.com/bitbucketserver/users-and-groups-776640439.html#Usersandgroups-Creatingauser) (limited to System Admin and Admin users)
2. For users who have their Bitbucket Server accounts integrated with a SAML provider, make sure that you talk to your IT admin so that you can create a new user in your SAML provider to be used as a service account.
3. [Add your account to a group](https://confluence.atlassian.com/bitbucketserver/users-and-groups-776640439.html#Usersandgroups-Addinguserstogroups).
4. Make sure the account has [read/write access to the repositories](https://confluence.atlassian.com/bitbucketserver/using-repository-permissions-776639771.html) you want to use in Stoplight.

### Azure DevOps Server

1. [Add a new account in your Azure DevOps Server instance to your organization](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/add-organization-users?view=azure-devops\&tabs=current-page#add-users-to-your-organization)
2. For users who have their Azure DevOps Server accounts integrated with a SAML provider, talk to your IT admin so that you can create a new user in your SAML provider to be used as a service account.
3. Make sure the account has read/write access to your repositories based on [**Access Level**](https://docs.microsoft.com/en-us/azure/devops/organizations/security/access-levels?view=azure-devops-2020) and [**Security Groups**](https://docs.microsoft.com/en-us/azure/devops/organizations/security/permissions-access?view=azure-devops-2020#git) assigned to it.

## Create a Personal Access Token in Your Git Provider

The second step in setting up Service Accounts is creating a personal access token.

Personal access tokens allow users to access information on their accounts by using a token in place of their password. Tokens also have the advantage of being able to be configured with `scopes`, so they have can have limited permissions to access information or to perform actions in your account, as well as an expiration date.

> For providers that allow expiry dates to be set for personal access tokens, Stoplight recommends setting them to not expire. If that's not possible, because of the provider settings or security policies, set a reminder to update your project with a new token close to the token's expiration date.
>
> This is to prevent users from being unable to make changes to their Stoplight project. If a project has a service account configured and the token expires, users won't be able to make any changes to the project until the personal access token is updated, or the service account configuration is removed.

### GitHub

To create a personal access token in GitHub:

1. If you have a GitHub account, select [this link](https://github.com/settings/tokens/new?description=stoplight\&scopes=repo) to open a page on GitHub pre-filled with a description and the required scopes for your personal access token.

Or:

1. Log in to your GitHub account.
2. Go to the Settings page, select **Developer settings** on the left side menu, and then [**Personal access tokens**](https://github.com/settings/tokens).
3. Select **Generate new token**.
4. Enter a name for the token on the **Note** field.
5. Select the **Expiration** time for the token, and make sure to select the scope `repo`.
6. Select **Generate token**.
7. Save the token for use in the next section.

You can find more details about generating a new personal access token in the [GitHub documentation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token).

### GitLab

To create a personal access token in GitLab:

<!-- markdown-link-check-disable-next-line -->
1. If you're using GitLab's SaaS offering, select [this link](https://gitlab.com/-/profile/personal_access_tokens?name=Stoplight\&scopes=write_repository) to open a page on GitLab pre-filled with a description and the required scopes for your personal access token.

Or:

1. Log in to your GitLab account.
2. Select your avatar on the top-right corner, and select **Edit profile**.
3. On the left side menu select **Access Tokens**.
4. Enter a name for the token and make sure to select the scopes `write_repository`.
5. Select **Create personal access token**.
6. Save the token for use in the next section.

You can find more details about generating a new personal access token in the [GitLab documentation](https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html).

### Bitbucket Cloud

Bitbucket Cloud uses "App Passwords" in place of Personal Access Tokens, but they work similarly. To create an app password in Bitbucket Cloud:

1. Log in to your Bitbucket Cloud account.
2. Select your avatar on the top-right corner, and select **Personal settings**.
3. On the left side menu select **App passwords** under **Access Management**.
4. Select **Create app password**.
5. Enter a name for the token and make sure to select the permissions:
   - Repositories: Read
   - Repositories: Write
6. Select **Create personal access token**.
7. Save the token for use in the next section.

You can find more details about generating a new app password in the [Bitbucket Cloud documentation](https://support.atlassian.com/bitbucket-cloud/docs/app-passwords/).

### Bitbucket Server

To create a personal access token in Bitbucket Server:

1. Log in to your Bitbucket Server account.
2. Select your avatar on the top-right corner, and select **Manage account**.
3. On the left side menu select **Personal access tokens**.
4. Select **Create a token**.
5. Enter a name for the token and make sure to select the permissions:
   - Projects: Write
   - Repositories: Write
6. Depending on your systems administrator settings, you might be required to set an expiry date for the token.
7. Select **Create**.
8. Save the token for use in the next section.

You can find more details about generating a new personal access token in the [Bitbucket Server documentation](https://confluence.atlassian.com/bitbucketserver/personal-access-tokens-939515499.html).

### Azure DevOps Server

To create a personal access token in Azure DevOps Server:

1. Log in to your Azure DevOps Server account.
2. Select your avatar on the top-right corner, and select **Security**.
3. On the left side menu select **Personal access tokens**.
4. Select **Add**.
5. Enter a name for the token in the **Description** field and make sure to select the permissions:
   - Code (read and write)
6. Select the expiration time for the token in the **Expires in** field.
7. Select **Create Token**.
8. Save the token for use in the next section.

You can find more details about generating a new personal access token in the [Azure DevOps Server documentation](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops\&tabs=Windows).

## Manage a Service Account

### Add a Service Account to Your Project

To add a service account to your project, you need to be a Workspace Owner, or a Project Owner/Admin.

1. Select your project from the Project List and select the **Settings** icon.
2. Scroll down to the Version Control Service Account section.
3. Select **Edit Information**.
4. Add your Service Account username to the Username field.
5. Add your provider authentication key (personal access token or app password) to the Authentication Key field.
6. Select **Test** to test the integration.
7. If everything is working correctly, select **Save Information**.
8. Select **Save** in the popup dialog.

And you're all set. Stoplight will now use the service account credentials to do any Git operations for this project, and Stoplight users without a Git account should now be able to contribute to this project (as long as they have the [correct permissions](../l.project-roles.md#project-roles)).

### Edit a Service Account

To edit a service account in your project, you need to be a Workspace Owner, or a Project Owner/Admin.

1. Select your project from the Project List and select the **Settings** icon.
2. Scroll down to the Version Control Service Account section.
3. Select **Edit Information**.
4. Make any changes to your configuration.
5. Select **Test** to test the integration.
6. If everything is working correctly, select **Save Information**.
7. Select **Save** in the popup dialog.

### Delete a Service Account

To delete a service account in your project, you need to be a Workspace Owner, or a Project Owner/Admin.

1. Select your project from the Project List and select the **Settings** icon.
2. Scroll down to the Version Control Service Account section.
3. Select **Delete Information**.
4. Select **Delete** in the popup dialog.

After a service account is deleted, Stoplight will revert to using the credentials from the user to do any Git operations.
