---
tags: [Governance]
---

# Style Guide Overview

Stoplight style guides add consistency, reusability, and easy governance to your API program. Style guides contain rules that help you govern versioning, filtering, error formats, naming conventions, pagination, and more. Examples include:

- Ban the use of HTTP basic
- Verify that every endpoint has security settings
- Ensure URL standards are set and followed

Stoplight uses [Spectral](https://meta.stoplight.io/docs/spectral/ZG9jOjYx-overview) to validate your API designs based on enabled style guides. You'll receive immediate feedback in the **Validation List** as you work in Studio.

![style-guide-feedback2.png](https://meta.stoplight.io/api/v1/projects/cHJqOjI/images/GqiaANFtj80)

See [this blog](https://blog.stoplight.io/explore-these-top-api-style-guide-resources) to learn more about incorporating style guides into your governance program.

## Style Guide Types

There are three types of style guides:

1. **Public style guides**: Guides that come from external sources, including the [Stoplight Style Guide](https://apistylebook.stoplight.io/docs/stoplight-style-guide), which is automatically enabled for all API projects. Customers on Professional and Enterprise plans can enable other public style guides, then [reuse and customize rules](reuse-and-customize-rules.md) to fit the needs of their organization. 
2. **Local style guides**: Rules stored in an API project. You can't share local style guides with other projects.
3. **Workspace style guides**: Use a dedicated project type to create style guides, and then share them across projects, business units, or workspace groups.

Workspace owners and admins can set default style guides that are automatically enabled for new projects (Professional and Enterprise plans only). Owners and admins can also prevent project owners, admins, and editors from disabling default style guides. See [Workspace Settings](../2.-workspaces/workspace-governance.md) for details.

## Style Guide Organization

How you manage style guides depends on your organization, but here are some ideas for incorporating style guides into your governance program:

- **Global governance**: Create rules that apply to all APIs. For example, create a rule that targets the `contact` object and the `email` field to ensure that all APIs use the correct support email for your company.
- **Project overrides**: Certain teams may have governance needs that other teams don't. In this case, you can enable your company's global style guide for your project, and then disable rules that don't apply. You can also create local targets and rules that are needed for your API, but not others.
- **Organize style guides into groups**: Consider creating a governance group to organize all your style guides and other governance materials, such as an API program charter and reusability guidelines. 

## Style Guide Documentation

Once a style guide is published, documentation is available for each rule in the guide. Documentation isn't available for rules defined in local style guides, however.

Rules are listed by severity, then in alphanumeric order.

![style-guides-documentation.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/tvblLpW4NyQ)

## Style Guide Access

Style guide projects can be created in any plan level. You can also create local rules and targets in an API project.

To enable style guides in other projects, you must be on a professional or enterprise plan. 

|                                 | Free | Starter | Professional | Enterprise |
|---------------------------------|--------|--------|-------|-------|
| Create local style guides*      | ✅    | ✅     | ✅     | ✅     |
| Enable Stoplight style guide    | ✅    | ✅     | ✅     | ✅     |
| Create style guide projects     | ✅    | ✅     | ✅     | ✅     |
| Enable shared and public style guides      |        |        | ✅     | ✅     |
| Set default style guides for a workspace |      | | ✅     | ✅     |
| Allow disabling of default style guides |       | | ✅     | ✅     |

*Based on plan project limit.

## Limitations

Stoplight is actively improving style guides and many updates are in progress. Here are a few known limitations:

- The Rule Editor currently supports one property/field per rule. If you need to evaluate multiple fields, create a separate rule for each field. 
- Style Guides aren't available in Studio Desktop or in Stoplight CLI projects.

> Looking for these or other style guide improvements? Add a note to the Stoplight [roadmap](https://roadmap.stoplight.io/).

---

[What's Next Create Style Guide](a1.create-style-guide.md)