# FAQ

Below you will find answers to commonly encountered questions.

> If you are having trouble and cannot find a suitable answer, don't hesitate to [let us know](mailto:support@stoplight.io).

## Try It and Mocking

### Why is "Try It" returning network errors?

Try these solutions:

1. Verify that your computer is connected to the internet.

2. Make sure the API is running and available under the specified URL.

3. If you've checked all of the above and still experiencing issues, check if the API supports [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS). Requests from browsers will be blocked for APIs that do not have appropriate CORS headers set up for `*.stoplight.io.` 

<!-- markdown-link-check-disable -->
See our [Knowledge Base](https://support.stoplight.io/hc/en-us/articles/360046967991-Error-while-making-the-request-Network-Error-the-API-did-not-return-a-response) for guidance on resolving this error.
<!-- markdown-link-check-enable -->

### Why do I get 422 Unprocessable Entity Responses?

Stoplight uses the Fetch Standard to make Mock Server and Try-It requests from the browser. As a result, Studio Web returns a 422 Unprocessable Entity response when a GET is paired with a request body. This occurs because the request body isn’t transmitted by Fetch and therefore the request fails validation against the specification.

## Why are files missing from my project documentation?

Below are a few common reasons why APIs/models/articles may not show up in the
documentation for a Stoplight project.

### Is there a Stoplight Config file present in your repo?

Use the **Stoplight Config** (`.stoplight.json`) file to include or
exclude paths in your repository from being exposed in the documentation. Verify the project configuration to make sure the file you are looking for has
not been excluded (or the file is in the include path).

For more information on this feature, see [Project Configuration](./2.-workspaces/c.config.md).

### Is there a `toc.json` file present in your repo?

The `toc.json` file can be used to restrict what is published in the
documentation view for a project. This is useful for controlling the
presentation of the sidebar.

If you have a `toc.json` file present in your project, double check the contents
to make sure the files you want to publish are listed. 

For more information on this feature, see
[here](4.-documentation/Sidebar/d.table-of-contents.md).

### Is the branch you are on published in the project settings?

Verify that the branch you are pushing your updates to is published and
listed. The published and available branches can be found under the project
**Settings** page.

![Branch Overview](assets/images/branches-overview.png)

For more information on how to manage, expose, and re-label branches, see [Branch Management](2.-workspaces/h.branch-management.md).

### If all else fails, check the Automation tab

If your project is connected to a Git repository, use the **Automation** tab
in the project **Settings** page which should provide more information on what
events were received and if they were successfully published.

![Automation Tab](assets/images/automation-tab.png)

When reviewing the **Automation** tab, verify that recent pushes to the
repository are listed. If not, it may point to an issue with the webhook
configuration. Try re-installing the webhook to resolve.

Errors will be highlighted in red. Pending tasks are highlighted in purple. 

> If you are seeing errors or other issues, don't hesitate to reach out to
>[support@stoplight.io](mailto:support@stoplight.io) to investigate further.

## Why is there an "Others" section in the sidebar?

If you're seeing an "Others" section in the sidebar of your project documentation:

![Others](assets/images/others_missing_tag.png)

Grouping of operations is completed by the use of [tags](https://swagger.io/docs/specification/grouping-operations-with-tags/). To prevent an "Others" section from being generated, be sure to add at least one tag to each endpoint and model in your project.

<!-- theme: warning -->

> When adding a tag to a model, an [OpenAPI Extension](https://swagger.io/docs/specification/openapi-extensions/) must be used. This can be added using the <i class="fal fa-tags"></i> icon in the editor to apply a tag or manually within code view.
![x-](assets/images/openapi_extension.png)

You can find more information on the default order of the project sidebar (as well as how to customize it) [here](https://meta.stoplight.io/docs/platform/4.-documentation/d.table-of-contents.md).

## What are the differences between Original, Bundled, Dereferenced.
1. Original - is the raw file keeping the $refs
2. Bundled - resolves remote $refs once, re-referencing the same objects in subsequent references (producing a smaller file)
3. Dereferenced - resolves all $refs, inserting each resolved reference inline

## Does Stoplight support adding HTML to documentation?

HTML support within Markdown is limited. See our [Markdown documentation](https://meta.stoplight.io/docs/studio/docs/Documentation/03-markdown-basics.md) for more information.

## How do I allow Stoplight to access an internal Git provider?

All network traffic from Stoplight originates from a fixed IP address. This is done so that network administrators can allow Stoplight to access your internal Git or identity providers with minimal risk to your network.

The fixed IP address is: **35.226.194.249**

## What browsers does Stoplight support?

We aim to support the following browsers and minimum versions. 

|               | Chrome | Safari        | Firefox | Edge          |
| ------------- | ------ | ------------- | ------- | ------------- |
| Documentation | 90     | 14            | 91      | 95            |
| Platform      | 90     | 14            | 91      | 95 |
| Studio        | 90     | Not Supported | 91      | Not Supported |

Things may work outside of these browsers and these versions, but there might be unexpected problems as we won't be testing those environments.

If something is not working in a version listed here (or newer) please [contact support](mailto:support@stoplight.io).

## Can't find GitHub Organization 

This could be due to missing permissions in GitHub. Navigate to https://github.com/settings/applications and find the Stoplight app. Click on it to go into the settings.

![GitHub Organization Access](assets/images/organization-access.png)

Notice the organization access at the bottom. Grant access to the organization you're looking to add repos from. You should then be able to add projects from your organization.

## What languages are supported?

Today Stoplight is only available in the English language. While it is possible
to host your own content in Stoplight that is not English, you may experience
minor errors and other discrepancies when using non-Latin letters or scripts
(ie, Cyrillic-based characters). For example, only the Latin alphabet is
supported in Stoplight's search functionality.

For any questions or concerns, please [contact Stoplight
Support](mailto:support@stoplight.io).
