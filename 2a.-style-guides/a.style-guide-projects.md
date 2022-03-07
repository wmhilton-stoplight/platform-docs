---
tags: [Governance]
---

# Overview

<!-- theme: info -->
>Shared style guides are available on the **Professional** and **Enterprise** plans.  

Stoplight style guides add consistency, reusability, and easy governance to your API program. Style guides contain rules that help you govern versioning, filtering, error formats, naming conventions, pagination, and more. Examples include:

- Ban the use of HTTP basic
- Verify that every endpoint has security settings
- Ensure URL standards are set and followed

Stoplight uses [Spectral](https://meta.stoplight.io/docs/spectral/ZG9jOjYx-overview) to validate your API designs based on enabled style guides. You'll receive immediate feedback in the **Validation List** as you work in Studio.

![style-guide-feedback2.png](https://meta.stoplight.io/api/v1/projects/cHJqOjI/images/GqiaANFtj80)

See our [rule examples](g-rule-examples.md) to get started.

## Style Guide Types

There are three types of style guides:

1. **Stoplight Style Guide**: This default style guide is always enabled for projects. You can use the style guide as it is, disable individual rules, or disable the entire style guide.
2. **Local style guides**: Rules are ceated within an API project. You cannot share local style guides with other projects.
3. **Shared style guides**: Use a dedicated project type to create style guides managed by workspace owners and administrators, and then share them across projects, business units, or workspace groups. 

[Depending on your plan](#style-guide-access), you can enable multiple style guides in an API project. For example, you can enable a global sytle guide that contains rules that apply to all APIs designed by your organization, and then enable a style guide that contains rules specific to your team or project. 

## Style Guide Organization 

How you manage style guides depends on your organization, but here are some ideas for incorporating style guides into your governance program:

- **Global governance**: Create rules that apply to all APIs. For example, create a rule that targets the `contact` object and the `email` field to ensure that all APIs use the correct support email for your company.
- **Project overrides**: Certain teams may have governance needs that other teams don't. In this case, you can enable your company's global style guide for your project, and then disable rules that don't apply. You can also create local targets and rules that are needed for your API, but not others. 
- **Organize style guides into groups**: Consider creating a group to organize all of your style guides. This will make it easier for those enabling style guides and those who review and maintain them. 

When a shared style guide is updated, you can apply those updates to your project to ensure you're always using the latest version.

## Style Guide Documentation

Once a style guide is published, documentation is available for each rule in the guide. Documentation is not available for rules defined in local style guides, however.

![style-guides-documentation.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/tvblLpW4NyQ)

## Style Guide Access

|                                 | Free | Starter | Professional | Enterprise |
|---------------------------------|--------|--------|-------|-------|
| Create local style guides*      | ✅    | ✅     | ✅     | ✅     |
| Enable Stoplight style guide    | ✅    | ✅     | ✅     | ✅     |
| Create style guide projects     |        |        | ✅     | ✅     |
| Enable shared style guides      |        |        | ✅     | ✅     |

*Based on plan project limit.

[What's Next: Create Style Guide](a1.create-style-guide.md)


