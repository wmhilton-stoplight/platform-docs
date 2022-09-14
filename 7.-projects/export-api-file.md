# Export from Stoplight

Stoplight offers multiple export options.


From published documentation (view mode), you can export:

* Individual API documents in a project, including models included in the specification.
* Individual models.

From the Design Editor (edit mode), you can export:

* An entire project, including all API documents, models, and Markdown articles. 
* Any individual file in a project.

## Export API Documents

API documents are exported from the published documentation view or from Explorer. This enables your API consumers to obtain API specifications on their own.

### $ref Options

There are two options for exporting references:

* **Original**: $refs are exported but not resolved.
* **Bundled References**. All $refs are resolved and placed in the components section so there is no duplication.

The following images show an example of both options. An export with the original option is on the left; bundled references are shown on the right.

![$Ref Export Examples](https://stoplight.io/api/v1/projects/cHJqOjI/images/UxXy5sQvKM4)

### Export an API from Documentation

1. Log in to your workspace, and then select the project you want to export.

2. Select:
   * The API overview (shown in the following example) to export all endpoints and models.
   * A single model.

3. Select **Export**, and then select a [reference option](#$ref-options).
![export_studioexport.png](../assets/images/export_studioexport.png)

### Export APIs with Explorer

1. Log in to your workspace, and then select **Explore** on the left pane.
2. Find the project you want to export.
3. Within the project, select the API overview (shown in the following example) or a single model.
4. Select **Export**, and then select a [reference option](#$ref-options).
![export_selectexport.png](../assets/images/export_selectexport.png)

## Export an Entire Project

This option exports all API descriptions and markdown files into a zip file.

Downloading projects resolves $refs in API and JSON Schema files. Design library users can view references to models in the design library.

### Download Projects with Studio Web

1. Log in to your workspace, then select the project you want to download, and then select **Edit**.
2. From the menu, select **Download Project Zip**.

![export_studiodownload.png](../assets/images/export_studiodownload.png)

### Download Projects with Studio Desktop

1. Open the project you want to download.
2. From the menu, select **Open project folder**.
3. In the dialog, select **Open** to navigate to the folder.
4. Use a local zip tool to create a zip file of the folder contents.

## Export Single Files

Use this option to export individual files in your project. The steps apply to Studio Web and Studio Desktop.

1. Log in to your workspace, and then edit a project.
2. Select the **Files** tab.
3. Right-click on the file you want to export.
4. Select **Export**.

For API files, the **Export** dialog opens. Select from these options:

- **Format**: Select **JSON** or **YAML** as the exported format. This is an easy way to convert a YAML file to JSON or vice versa.
- **References**: Select **Bundled** to resolve $refs and place them in the components section. Select **Dereferenced** to export $refs as unresolved.
- **X-Extensions**: Select **Included** to export [extensions](../3.-design/x-extensions.md) included in the API.
- **Copy to clipboard** or **Save to file**: Select one of these options.

For other file types, choose to **Copy to clipboard** or **Save to file**.

