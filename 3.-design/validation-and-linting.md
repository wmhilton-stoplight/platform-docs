---
tags: []
---

# Validation and Linting

Studio automatically:

* Validates YAML and JSON files.
* Lints OpenAPI v2 and v3.x specifications based on a default ruleset. 
* Lints Markdown articles for broken image URLs for local files.

The following example shows two JSON errors and four style guide warnings in the **API Design Checker** for an OpenAPI description. Select each item in the list to go directly to the line that needs attention.

![Validation and Linting](https://stoplight.io/api/v1/projects/cHJqOjI/images/0udu5kiydHA). 

> The Style and Validation rule engine is powered by the open-source project [Spectral](https://stoplight.io/open-source/spectral). 

### Validation Rules

Validation rules signify whether your generic JSON/YAML and API descriptions are technically correct. An example validation rule is one that requires a unique `operationId` for every operation.

> **Tip**:
> Validation is available for the [Table of Contents file](../4.-documentation/Sidebar/d.table-of-contents.md) used to organize the project sidebar.

### Style Rules

Style rules differ from validation rules because they provide guidance for naming conventions, missing information which would improve the quality of documentation, and more.

Depending on the ruleset, the **API Design Checker** can show warnings, errors, informational messages, and hints.

Each Stoplight API project is automatically linted using the [Stoplight Style Guide](https://apistylebook.stoplight.io/docs/stoplight-style-guide). You can disable rules in this guide, change their severity (error to warning, for example), and add your own rules. See [Stoplight Style Guides](../2a.-style-guides/a.style-guide-projects.md) for more information.

### Markdown Linting

When editing Markdown articles, the **Docs Checker** pane will display an error if you have a broken image URL of a local file.

![Stoplight editor, showing the Docs Checker pane with an error message saying "Broken markdown image URL:," the path to the broken image file, and the line where it's located](../assets/images/lint-broken-images.png)
