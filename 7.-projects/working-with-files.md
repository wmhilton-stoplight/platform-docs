---
tags: []
---

# Work with Files

Once you create an API project, add files to start designing APIs and documentation. 

These file types are supported:

- **API**: API description documents (YAML or JSON)
- **Endpoint**: Individual paths and operations (YAML or JSON)
- **Model**: Reusable API components (YAML or JSON)
- **Article**: Supplemental Markdown files (Markdown)
- **Image**: Supplemental images (JPEG, JPG, PNG, and GIF)
- **Configuration Files**: The Stoplight [project configuration file](../2.-workspaces/c.config.md), [table of contents file](../4.-documentation/Sidebar/d.table-of-contents.md), and [imported Spectral files](../2a.-style-guides/style-guides-and-git.md) (Git projects only). 

<!-- theme: Warning -->
>**Warning**: You may be able to upload other file types, but they may not be rendered in Studio or in published documentation.

## Directory Structure

Projects use a default file directory structure. 

- `/root` - Stoplight configuration files
- `/reference` - API descriptions documents (OpenAPI and JSON Schema)
- `/models` - Shared models
- `/docs` - Articles (Markdown files)
- `/assets/images` - Imported images

If you have an existing repository with Markdown, image, or API description documents that don't adhere to the format above, you will need to move the files to their corresponding directories for Studio to recognize them, or create a [project configuration file](../2.-workspaces/c.config.md) to change them.

## Add a File

1. Edit an API project.
2. Select **Add (+)**, and then select the type of file to add.

### API

**Create New File**: Create a new API from scratch by providing a name, OpenAPI version, and format (YAML or JSON).

**Import Existing Files**: You can also import an existing YAML or JSON OpenAPI file, or import a [Postman Collection](../6.-migrations/postman.md) file.

### Endpoint

Select the API to add the endpoint. Select or create a tag to group similar endpoints together. Provide a path. 

### Model

Provide a name, then select or create a tag to group similar models together. Select a scope. (Common models are accessible to all APIs within your project.) Choose YAML or JSON format or select **Import Existing** to add an existing YAML or JSON OpenAPI file.

### Article

Provide a short title and a tag to group similar articles together.

### Stoplight Config

Used to control file locations and exclude locations from being analyzed by Stoplight. See [Configure Projects](../2.-workspaces/c.config.md).

### Image

If your project is connected to a public Git repository, use the **Import File** option to add images. Otherwise, drag images onto Markdown files to add them to Stoplight. See [adding images](../4.-documentation/f.adding-images.md) for details.

### Table of Contents

Use to configure the project sidebar. See [Project Sidebar](../4.-documentation/Sidebar/a.customize-sidebar.md).

### File

Adds a generic file to the tree. Unsupported file types won't be rendered in published documentation, but you can add information that may be useful to your project.

### Directory

Adds a folder that you can use to organize content. This is especially useful for documentation files. Keep in mind that if you want to use a custom folder structure, you must use a [project configuration file](../2.-workspaces/c.config.md).

### Import Style Guide

Use to add a Spectral ruleset to an API project. This action replaces all local rules, targets, and custom functions in an API project. It doesn't impact rules, targets, and functions that are inherited from an enabled style guide. See the [Style Guides documentation](../2a.-style-guides/a.style-guide-projects.md) for more information.

### Import File

Use to add images and other files. Files are automatically organized by type. For example, Markdown files are automatically added to the `Docs` directory; image files are automatically added to the `assets` folder. 

### Import Directory

Imports a directory of files to your project. This is useful for migrating content into Stoplight. 


