# Bitbucket Server

> This feature is only available on the **Pro** plan and above.

Configure your Bitbucket Server integration by following these instructions.

1. Select **Settings** from the workspace home page, then navigate to the **Integrations** section.
2. Select **Add** for Bitbucket Server, then add the following information:
   - **Name**: Enter a Name (e.g `Stoplight Integration`).
   - **API URL**: This is the URL of the API of your instance of Bitbucket Server. This is usually: `{HostURL}/rest/api/1.0`, where the HostURL is the URL where your instance of Bitbucket Server is hosted.
3. Test your settings.
4. Select **Save**.

## Firewall and Fixed IP Address Configuration

All network traffic from Stoplight originates from a fixed IP address. This is done so that network administrators can allow Stoplight to access your internal Git or identity providers with minimal risk to your network.

If your self-hosted Git provider is behind a firewall, add our fixed IP address **35.226.194.249** to your allowlist on port 443 over HTTPS.

## Troubleshooting

See [Troubleshoot Git](f-troubleshoot-git.md) for guidance on resolving connection issues. 
