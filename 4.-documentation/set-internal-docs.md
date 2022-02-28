# Set Article Visibility

You can prevent articles from being visible to external users or users who are not members of a workspace. Internal articles are no longer visible in the Table of Contents or searchable for these users.

You may want to hide articles when:

- An article is in draft form. This is especially useful for web projects because it allows you to stage articles before making them public.
- An article contains internal notes that you want visible to workspace members, but not to public users. This is useful for linking to other articles and API elements in the same project without exposing your internal notes. 

To set a Markdown article as internal:

1. Open a markdown article.
2. Set the **Visibility** to internal.

The `internal: true` tag is added to the topic. If you remove the tag, the **Visibilty** flag is set to false.

![internal-markdown-articles.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/3yM8E8Dbo8I)

 **Tip**: You can also set endpoints and models to have internal visibility. This prevents them from being exported and being included in public API documentation.

![internal-endpoints.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/9nA4f9B8ocM)