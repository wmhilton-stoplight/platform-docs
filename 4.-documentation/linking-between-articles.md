---
tags: []
---

# Add Links to Articles

Add hyperlinks to other Markdown files or API elements to your documentation files. 

## Link to API Elements

### API Overview

1. Select the **APIs** tab, and then right-click **API Overview** in the left pane.

2. Select **Copy Path**. 

![link-api-overview.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/Rr0cCDrLpB0)

3. Open the **Markdown file** you want to add links to.

4. Add the link in this format:

   `[Display text](reference/your-api-file.yaml)`

### Endpoints

To reference an endpoint from within the API specification, first build the relative path to the `api.yaml` or `api.json` file, and then the path to the API endpoint call. 

1. Select the **APIs** tab, and then right-click the .yaml or .json file that contains the endpoint you're linking to.

2. Select **Copy Relative Path**. Paste the copied path to the **Markdown file** you want to add links to or another location.

3. From the **APIs** tab, open the API you are linking to, and then right-click the endpoint you want. Select **Copy Path**.

4. Use the two copied links to build a URL in this format:

   `[Display text](../reference/-your-api-file.yaml/paths/~1endpoint-name)`

5. Append the HTTP request method to the end of the URL. Example:

   `[creating a verification](../reference/your-api-file.yaml/paths/~1verification-requests/post)`

> **Note**: The copied path does not include the HTTP request method. You will need to append that yourself.

### Models

1. Select the **APIs** tab, and then right-click the model you want to link to.

2. Select **Copy Path**. 

3. Open the **Markdown file** you want to add links to.

4. Add the link in this format:

   `[Display text](your-api-file.yaml/components/schemas/modelname)`

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

