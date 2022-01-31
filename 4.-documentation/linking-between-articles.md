---
tags: []
---

# Link Between Articles

## What

Add hyperlinks to other Markdown files or API elements to your documentation files. All links are relative to the current file. Use `%20` to escape spaces in file names.

## How

1. Open the **Markdown file** you want to add links to.

2. Right-click the file you're linking to, and then select **Copy Relative Path**. To reference an element from within the API specification, first build the relative path to the `api.yaml` or `api.json` file (ie `../reference/api.yaml`) and then the path to the API endpoint call. 

> **Note**: The copied path does not include the HTTP request method. You will need to append that yourself.

![endpoint-links.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/qSyOR4k4rFU)

3. Add the link in this format: `[Display Text](Hyperlink URL/File Location)`

   **Markdown example**: `[Types of Documentation](../4.-documentation/b.types-of-documentation.md)`

   **API Method Example**: `[creating a verification](../reference/api.yaml/paths/~1verification-requests/post)`

