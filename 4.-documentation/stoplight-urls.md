---
stoplight-id: af3cc200b40c3
---

# Stoplight URLs

Conceptually, there are two types of URLs for Stoplight projects:

* **[Published URLs](#about-published-URLs)**: Links for published API and Markdown files. These are also referred to as "permalinks." 
* **[Relative Links](#about-relative-links)**: Links inside an API artifact or Markdown article to another artifact or article in the same project. For example, use relative links to direct users from an API getting started article to another article or an API endpoint.

## About Published URLs

Published API, model, and article URLs have unique identifiers referred to as stable IDs. Each API, model, and Markdown file has one stable ID. By default, stable IDs are visible in the published URL and are automatically set based on the location of a source file within the project file directory. 

By default, URLs for published API, models, and articles follow this format:

`/docs/{projectSlug]/{stableID}-{title}`

For example, in this published URL of a Markdown article:

`https://meta.stoplight.io/docs/platform/ZG9jOjMwNDI1OTM1-rule-examples`

* `https://meta.stoplight.io/docs` is the workspace URL or custom domain, along with /docs prefix, which is present for all project documentation.
* `platform` is the project's `slug` value. This can be changed in the [Project Settings](../7.-projects/project-settings.md).
* `ZG9jOjMwNDI1OTM1` is the stable ID.
* `rule-examples` is the title of the article in slug format.

### About Stable IDs

Stable IDs:

- Enable you to move and rename files without breaking published URLs. 
- Enable you to change article titles without breaking published URLs.
- Hide the underlying directory structure, which makes the URL smaller.

> If you move or rename files, you must manually change the relative links to those files and in the [Table of Contents](Sidebar/d.table-of-contents.md). For example, if you add a link to one Markdown article in another article and you later move the referenced file, you must adjust the reference to point to the moved file.

Use slugs to remove stable IDs from published URLs. See [Change Published URLs](#change-published-urls).

### Stable ID Formats

Stable IDs are used to formulate the published URLs and are automatically added to new, imported, and renamed files. The formats are different for Markdown articles and API files.

```markdown title="Markdown Articles"
---
stoplight-id: ueil0179cp07l
---
```

----

```yaml title="API and Schema Files"

x-stoplight:
  id: pqxhxyu95h4pz
```

### Stable ID Guidelines

<!-- theme: warning -->
> **Warning**: Don't delete or modify the stable IDs. Doing so may cause the associated published URL(s) to change, potentially breaking bookmarks or backlinks to your docs.

* The x-stoplight.id format is valid for OpenAPI and shouldn't affect third-party tooling. 
* You can ignore stable IDs, but you should never delete them.
* For API files, published URLs for endpoints and models have different stable IDs. 
* If you delete a file from Stoplight, and later re-import it, the imported file will be assigned a new stable ID if one isn't found in its contents. You may do this if you are managing an OpenAPI file in another tool, for example. To ensure your stable IDs stay in sync, add the Stoplight stable ID to the file in your external system, so that when it's re-imported, it won't be assigned a new stable ID.

### Change Published URLs

If you need more control over published URLs, you can add slugs to the [Table of Contents](Sidebar/d.table-of-contents.md) file for API and Markdown articles. This removes the stable ID from the URL and allows you to control the URL ending. 

When you set a slug for a given item, the previous stable-ID-based URL automatically redirects to the new slug-based URL. This allows you to incrementally introduce custom-slug-based URLs to your project without breaking user bookmarks or backlinks that might be pointing to the old stable-ID-based URLs.

Slugs are particularly useful for API files because they extend to all operations and models in the file. 

#### Slug Guidelines

* Plan your taxonomy before you implement slugs. Once slugs are implemented, you should avoid changing them since doing so will change the published URLs.
* Slugs must be unique within a project.

#### API Example

The following example assumes that the API contains:

* These paths: `/users/{userId}` and `/user`
* These operations: `Get User`, `Update User`, and `Create New User`
* A User model

<!-- title: Your toc.json File -->
```json
{
  "items": [
    {
      "type": "item",
      "title": "Payments API",
      "uri": "/reference/payments.openapi.yaml",
      "slug": "payments-api"
    }
  ]
}

```
**API result**: 

`docs/{project-slug}/payments-api`

**API operation results**: 

`docs/{project-slug}/payments-api/operations/get-a-user`

`docs/{project-slug}/payments-api/operations/modify-a-user`

`docs/{project-slug}/payments-api/operations/create-a-user`

**Model result**: 

`docs/project-slug/payments-api/schemas/user`

#### Markdown Examples

<!--
title: Simple Markdown Slug
-->
```json
{
  "items": [
    {
      "type": "item",
      "title": "Introduction",
      "uri": "/docs/introduction.md",
      "slug": "api-intro"
    }
  ]
}
```
**Markdown Result**: 

`docs/project-slug/api-intro`

<!--
title: Markdown with Nested Slug
-->
```json
{
  "items": [
    {
       "type": "item",
       "title": "Authentication Intro",
       "uri": "/docs/authentication-intro.md",
       "slug": "auth/intro"
    }
  ]
}
```
**Markdown Result**: 

`docs/project-slug/auth/intro`

## About Relative Links

Use these options to add hyperlinks to other Markdown files or API elements: 

* **Copy Path**: Copies the full path of the selected file. The full path starts at the root directory.
* **Copy Relative Path**: Copies the path relative to the file you have open in the Editor when you right-click on a file in the **Files** tab. 

You can link to API elements or Markdown files.

### Link to API Elements

#### API Overview

1. Select the **APIs** tab, and then right-click **API Overview** in the left pane.
2. Select **Copy Path**. 

![link-api-overview.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/Rr0cCDrLpB0)

3. Open the **Markdown file** you want to add links to.
4. Add the link in this format:
   `[Display text](../reference/your-api-file.yaml)`

#### Endpoints

To reference an endpoint in a Markdown file:

1. From the **APIs** tab, open the API you are linking to, and then right-click the endpoint you want to link to.
2. Select **Copy Path**.
3. Paste the path into your Markdown file, using this format:
        `[Display text](reference/-your-api-file.yaml/paths/~1endpoint-name)`.
4. Prepend `../` to the beginning of the URL. 
4. Append the HTTP request method to the end of the URL. Final example:
        `[Display text](../reference/your-api-file.yaml/paths/~1verification-requests/post)`.

> **Note**: The copied path doesn't include the HTTP request method. You will need to append that yourself.

To add operations links to API descriptions in the same specification file, use the encoded JSON path. Example:
        `[Display text](paths/~1users~1{userId}/get)`

#### Models

1. Select the **APIs** tab, and then right-click the model you want to link to.
2. Select **Copy Path**. 
3. Open the **Markdown file** you want to add links to.
4. Add the link in this format: `[Display text](your-api-file.yaml/components/schemas/modelname)`

### Link to Other Markdown Articles

1. Select the **Docs** tab.

2. Open the **Markdown file** you want to add links to.

3. From the left pane, locate the file you want to link to.
   * For files in the same folder, right-click and select **Copy Relative Path**. 
   * For files in a different folder, right-click and select **Copy Path**.

4. Add the links in the correct format. Examples:

   `[File in a different folder](../folder-a/my-markdown-file.md)`

   `[File in the same folder](my-markdown-file.md)`

## FAQs

### How can file names be escaped?
   
Use `%20` to escape spaces in file names.
   
### Which option adds topics to the project sidebar?
   
When adding topics to the [project sidebar (table of contents)](Sidebar/d.table-of-contents.md), always use the relative path.