# Git Overview

Stoplight can connect with popular Git Providers hosted publically or on your servers (even if it's protected by a firewall), letting you work directly with [projects](../../7.-projects/adding-projects.md) in public or private repos. 

## Git Provider Support

We support the following Git providers.

- <i class="Icon fab fa-bitbucket fa-2x" style="color: rgb(32, 80, 129);"> </i> Bitbucket Cloud

- <i class="Icon fab fa-bitbucket fa-2x" style="color: rgb(32, 80, 129);" > </i> Bitbucket Server

- <i class="fab fa-github fa-2x"> </i> Github

- <i class="Icon fab fa-gitlab fa-2x" style="color: rgb(252, 109, 38);"> </i> GitLab

- <i class="Icon fab fa-microsoft fa-2x" style="color: rgb(32, 80, 129);"> </i> Azure Devops

If you don't see the Git Provider you're looking for, take a look at our [roadmap](https://roadmap.stoplight.io/) to keep an eye on what's coming next. You can also use [Stoplight CLI](../f.working-with-local-projects.md) to push projects to the Stoplight Platform.

## Configure Cloud Git Providers

Cloud-hosted Git providers are configured out of the box in Stoplight. The following cloud Git providers are supported:

- <i class="Icon fab fa-bitbucket fa-2x" style="color: rgb(32, 80, 129);" > </i> Bitbucket Cloud

- <i class="fab fa-github fa-2x"> </i> Github

- <i class="Icon fab fa-gitlab fa-2x" style="color: rgb(252, 109, 38);"> </i> GitLab

1. Select **Settings** from the workspace home page.
2. From the **Integrations** section, select **Add** next to your preferred Git provider.
3. Select **Use Default Configuration,** and the select **Save**. 

If you have a self-hosted deployment or are looking for custom integration settings, use the guides below.

## Configure Self Hosted Git Providers
<!-- theme: warning -->
> This feature is available on the **Pro** plan and above

Configure your Git provider using the guides below:

- [Bitbucket Cloud](b.bitbucket-cloud.md)
- [Bitbucket Server](c.bitbucket-server.md)
- [GitHub Enterprise](d.github-enterprise.md)
- [GitLab](e.gitlab.md)

### Firewall and Fixed IP Address Configuration

All network traffic from Stoplight originates from a fixed IP address. This is done so that network administrators can allow Stoplight to access your internal Git or identity providers with minimal risk to your network.

If your self-hosted Git provider is behind a firewall, please add our fixed IP address **35.226.194.249** to your allowlist on port 443 over HTTPS. 