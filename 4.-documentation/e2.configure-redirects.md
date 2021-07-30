# Redirects

![Redirects](https://stoplight.io/api/v1/projects/cHJqOjI/images/U8WhIievrnY)

## Overview

Want to move your documentation pages without breaking old links? You can manually configure redirect rules for paths on your Workspace's custom domain.

> This feature is available on the [Stoplight **Starter** plan](https://stoplight.io/pricing/), and above.

## How it works

Within your Stoplight Workspace, you can configure redirect rules and a custom domain. When someone navigates to a path matching one of your custom domain's redirect rules, they will automatically be redirected to the new path.

Here are the steps to get started:

1. Navigate to your Stoplight workspace settings and [configure your custom domain](../2.-workspaces/j.custom-domains.md).
2. Click "Redirects" and add one or more redirect rules. Each redirect rule must be listed on a separate line, with the original path followed by a space then the new path. Lines beginning with `#` will be ignored.

![Redirects editor](https://stoplight.io/api/v1/projects/cHJqOjI/images/d6KLm6WIohc)

## Examples

### Redirect to a new path

Say you've moved one of your pages to a new location. You could add the following redirect rule:

```bash
# Old path         New path
/old/introduction /docs/my-project/introduction
```

Then when someone navigates to `https://your-domain.com/old/introduction`, they will automatically be redirected to `https://your-domain.com/docs/my-project/introduction`.

### Redirect all subpaths to a new path

Say you've removed several pages and want all links to them to land on a specific page. You could add the following redirect rule:

```bash
# Old paths     New path
/old/welcome/* /docs/my-project/introduction
```

Then when someone navigates to a subpath of `/old/welcome/` such as `https://your-domain.com/old/welcome/overview`, they will automatically be redirected to `https://your-domain.com/docs/my-project/introduction`.

### Redirect all subpaths to a matching subpath

Say you've moved several articles from one location to another. You could add the following redirect rule:

```bash
# Old paths    New paths
/old/guides/* /docs/my-project/*
```

When someone navigates to a subpath of `/old/guides/`, such as `https://your-domain.com/old/guides/quickstart`, they will automatically be redirected to a destination with the same subpath: `https://your-domain.com/docs/my-project/quickstart`.
