# Set Article and API Visibility

You can prevent articles, paths, and models from being visible to users who are not members of a workspace and guest users by marking those items as internal.

Internal items are no longer visible in the [Table of Contents](Sidebar/d.table-of-contents.md) or searchable for these users.

You may want to hide items when:

- An API operation on an otherwise publicly available API is only intended for internal use.
- A project or a repository contains a mix of public and internal APIs and you want to keep the documentation together in the same project.
- An article is in draft form. This is especially useful for web projects because it allows you to stage articles before making them public.
- An article contains internal notes that you want visible to workspace members (except for guests), but not to public users. This is useful for linking to other articles and API elements in the same project without exposing your internal notes.

## Set Article Visibility

To set a Markdown article as internal:

1. Open a Markdown article.
2. Set the **Visibility** to internal.

The `internal: true` tag is added to the topic. If you remove the tag, the **Visibilty** flag is set to false.

![internal-markdown-articles.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/3yM8E8Dbo8I)

## Set API Path and Model Visibility

To set an API path or model as internal:

1. Open the path or model.
2. Set the **Visibility** to internal.

![internal-endpoints.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/9nA4f9B8ocM)

The `x-internal: true` property is added to the path or model in the API specification file. This prevents them from being exported and included in the public API documentation.
