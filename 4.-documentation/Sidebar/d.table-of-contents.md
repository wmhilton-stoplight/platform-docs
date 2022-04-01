# Project Sidebar

Project documentation contains a single left sidebar called the **Table of Contents** (or ToC). The [default structure](#the-default-structure) of this sidebar loosely follows the file system of the project, with a few exceptions for APIs and models. 

You can customize the appearance of this sidebar using a Table of Contents file (`toc.json`), which supports:

- Customizing the order of files in the sidebar
- Overriding the title of a file in the sidebar
- Selectively exposing files in the sidebar, allowing you to hide items by not including them in your Table of Contents file
- Using redirects to send users to documentation files that have been moved or renamed. See  [Redirects](../e2.configure-redirects.md).

![studio demo documentation](../../assets/images/studio-demo-docs.png)

> ### Limitations
> 
> There are a few known limitations with this functionality:
> 
> 1. **You can only reorder articles, APIs, and model files.** Endpoints and internal models will follow the [default structure](#the-default-structure) outlined below. [(roadmap)](https://roadmap.stoplight.io/c/110-custom-ordering-for-endpoints-and-models)
> 2. **The `toc.json` file must be written by hand.** [(roadmap)](https://roadmap.stoplight.io/c/112-table-of-contents-editor)
> 3. **Renaming a file does not automatically update the `toc.json`.** You'll need to remember to update your TOC whenever a file is renamed. Otherwise your project sidebar might contain broken links. [(roadmap)](https://roadmap.stoplight.io/c/96-automatically-rewrite-references-and-links-on-filename-change)
> 

## Overview

There are three types of entities in the Table of Contents:

![toc element overview](../../assets/images/toc-overview.png)

### Dividers

Dividers are bold, non-clickable items that signify the start of a section of content within the sidebar.

### Groups

Groups are non-linkable, collapsible items containing items and other groups that all relate to the same subject matter. Dividers cannot be nested within a group.

### Items

Items are links to articles, APIs, and model files located within the project directory or external links to content outside of the documentation. Optionally, use the `title` property to override the item's default title in the table of contents.

## Add a TOC to a Project

1. Edit a project, and then select the **Add** icon.
2. Select **Table of Contents**. A toc.json file opens in the Editor panel. It is organized using the [default structure](#the-default-structure).
3. Organize items in the structure to meet your needs and add new items using the rules below. 
4. Select **Preview** to verify the structure.

Validation is provided to help you correct errors before you publish.

![toc-validation.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/5Tr1xFQBeg0)


To revert your changes, select **Generate Default Content** to return the toc.json file to its original state. 

## Create Your Own TOC

You can create a custom table of contents file. To get started, create a `toc.json` file in your project's **root directory**.

The `toc.json` file should start off with an empty `items` array where you will define your content structure using [dividers](#dividers), [groups](#groups) and [items](#items).

<!-- title: toc.json -->
```json
{
  "items": []
}
```

## TOC Rules

- Each entity should have a `type` and a `title` property. 
- Items should also have a `uri` property that either points to a file somewhere within the project or an external link to another website. 
- Groups should have an `items` property allowing you to futher nest more items and groups.

Press **CMD+Space** to open a list of hints for items you can add to the TOC.

> **TIP**: The easiest way to get a file's URI in Studio is right-click on the file, select **Copy Path**, and then paste the contents into the JSON file.
>

### Example

Here is an example to demonstrate the format of the `toc.json` file. 

<!--
title: toc.json
-->
```json
{
  "items": [
    {
      "type": "divider",
      "title": "Divider"
    },
    {
      "type": "item",
      "title": "Item",
      "uri": "docs/table-of-contents.md"
    },
    {
      "type": "group",
      "title": "Group",
      "items": [
        {
          "type": "item",
          "title": "Nested Item",
          "uri": "docs/nested-item.md"
        }
      ]
    },
    {
      "type": "item",
      "title": "External Link",
      "uri": "https://stoplight.io"
    }
  ]
}
```

The above `toc.json` file displays the following structure in the docs sidebar.

![custom toc example](../../assets/images/custom-toc-example.png)

## Endpoint Group Reordering

To reorder endpoint groups:

1. Create global tags. The easiest way to do this is to select the API overview from the **Form** view, select the tag icon, and then add tags.
<!-- focus: center -->
![global-tags.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/6qZrKIl2LCU)

2. Order the global tags. The easiest way to do this to switch to **Code** view, scroll to the bottom of the editor, and change the order of the tags.
<!-- focus: center -->
![reorder-tags.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/o2rWrFPDrpI)

3. Assign tags to each endpoint to determine which group it will be listed under.

4. Publish and review the results.
<!-- focus: center -->
![tag-order.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/UcWagdp1nqg)

## The Default Structure

When the `toc.json` file is not present, the default structure is organized based on a few factors, such as the file type, but primarily follows the same alphanumeric ordering of the filesystem.

### Articles

Markdown articles come first in the table of contents and are ordered alphabetically by their file path. The first directory is represented as a [divider](#dividers) and any directories after appear as [groups](#groups). 

- The Docs folder is flattened and is not represented in the table of contents. 
- Any articles located in the root of the project are sorted to the top. 
<!-- - If a `README.md` file exists, it is put in the first position.-->

### APIs

APIs are listed below articles. A [divider](#dividers) separates APIs from articles, and each API's title is represented as a group. This group contains overview information, such as the API's description, contact, licensing, servers and global security. 

### Schemas

At the bottom of the table of contents are JSON Schema model files that are outside of an API specification. Models are listed under a [divider](#dividers) titled **Schemas** and follow the order in the specification.

### Endpoint and Model Ordering Rules

- Endpoints or models without tags are placed at the root level and follow the order in the specification. 
- All API endpoints and models are nested inside [groups](#groups) titled after their first tag. 
- Within each group, endpoints and models follow the order in the specification.