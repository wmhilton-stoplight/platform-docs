---
tags: []
---

# Add Links

Use these options to add hyperlinks to other Markdown files or API elements: 

* **Copy Path**: Copies the full path of the selected file. The full path starts at the root directory.
* **Copy Relative Path**: Copies the path relative to the file you have open in the Editor when you right-click on a file in the **Files** tab. 

You can link to API elements or to Markdown files.

## Link to API Elements

### API Overview

1. Select the **APIs** tab, and then right-click **API Overview** in the left pane.
2. Select **Copy Path**. 

![link-api-overview.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/Rr0cCDrLpB0)

3. Open the **Markdown file** you want to add links to.
4. Add the link in this format:
   `[Display text](../reference/your-api-file.yaml)`

### Endpoints

To reference an endpoint in a Markdown file:

1. From the **APIs** tab, open the API you are linking to, and then right-click the endpoint you want to link to.
2. Select **Copy Path**.
3. Paste the path into your Markdown file, using this format:
        `[Display text](reference/-your-api-file.yaml/paths/~1endpoint-name)`.
4. Prepend `../` to the beginning of the URL. 
4. Append the HTTP request method to the end of the URL. Final example:
        `[Display text](../reference/your-api-file.yaml/paths/~1verification-requests/post)`.

> **Note**: The copied path does not include the HTTP request method. You will need to append that yourself.

To add operations links to API descriptions in the same specification file, use the encoded JSON path. Example:
        `[Display text](paths/~1users~1{userId}/get)`

### Models

1. Select the **APIs** tab, and then right-click the model you want to link to.
2. Select **Copy Path**. 
3. Open the **Markdown file** you want to add links to.
4. Add the link in this format: `[Display text](your-api-file.yaml/components/schemas/modelname)`

## Link to Other Markdown Articles

1. Select the **Docs** tab.

2. Open the **Markdown file** you want to add links to.

3. From the left pane, locate the file you want to link to.
   * For files in the same folder, right-click and select **Copy Relative Path**. 
   * For files in a different folder, right-click and select **Copy Path**.

4. Add the links in the correct format. Examples:

   `[File in a different folder](../folder-a/my-markdown-file.md)`

   `[File in the same folder](my-markdown-file.md)`

## Tips

   - Use `%20` to escape spaces in file names.
   - When adding topics to the [project sidebar (table of contents)](Sidebar/d.table-of-contents.md), always use the relative path.

