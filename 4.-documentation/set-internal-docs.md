# Set Article and API Visibility

You can hide APIs, paths, models, and articles from public documentation and guest users by marking those items as internal.

Internal items are no longer visible in the [Table of Contents](Sidebar/d.table-of-contents.md) or searchable for these users.

You may want to hide items when:

- An API operation on an otherwise publicly available API is only intended for internal use. In this case, set the operation as internal.
- A project or a repository contains a mix of public and internal APIs and you want to keep the documentation together in the same project. In this case, set the internal flag for APIs you want to hide.
- An article is in draft form. This is especially useful for web projects because it allows you to stage articles before making them public. In this case, set the internal flag for the Markdown file.
- An article contains internal notes that you want visible to workspace members (except for guests), but not to public users. This is useful for linking to other articles and API elements in the same project without exposing your internal notes. In this case, set the internal flag for the Markdown file.

## Set Article Visibility

To set a Markdown article as internal:

1. Select the **Docs** tab.
2. Open a Markdown article.
3. Set the **Visibility** to internal.

The `internal: true` tag is added to the topic. If you remove the tag, the **Visibility** flag is set to false.

![internal-markdown-articles.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/3yM8E8Dbo8I)

## Set API Visibility

You can set an API, path, or model as internal. 

When you set an entire API as internal, all of its endpoints and models are also set to internal. If you remove the internal flag for an API at a later time, the internal settings are preserved for models and endpoints. You must manually remove the internal flag for each element you want to be public.

To set an API, path, or model as internal:

1. Select the **API** tab.
2. Select the item to set as internal:
    * **Entire API**: Select **API Overview**.
    * **Path**: Select the path.
    * **Model**: Select the model.
3. Set the **Visibility** to internal.

![internal-endpoints.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/9nA4f9B8ocM)

The `x-internal: true` property is added to the API specification file for the items you hide. This prevents them from being exported and included in the public API documentation.
