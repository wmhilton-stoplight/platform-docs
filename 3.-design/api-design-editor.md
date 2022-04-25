# Design Editor Overview

Use the Design Editor, also referred to as Stoplight Studio, to design and manage APIs, documentation, and related files stored in projects. Projects work and look the same in Studio Web and Studio Desktop, with a few differences. This topic describes projects in Studio Web. 

## Open a Project

To open a project from the **Home** page:
   * Select the project from the project sidebar (left pane), or 
   * Select **Projects** from the tab the top of the page, and then select a project. 

Project owners, admins, and editors can select **Edit** to manage the project. 

## Use the Designer

Once you are editing a project, there are three key areas of the interface:
1. [Project sidebar](#project-sidebar)
2. [Project toolbar](#project-toolbar)
3. [Editor panel](#editor-panel)

![ui-overview.png](https://stoplight.io/api/v1/projects/cHJqOjI/images/3eJur8Cy6RA)

## Project Sidebar

Switch between tabs to work with project content:

- **APIs** lists APIs, endpoints, models, request bodies, responses, parameters, and examples.
- **Docs** lists Markdown and image files.
- **Files** lists all project files.
- **Styles** lists enabled style guides, rules, and targets.

Select an item on any tab to open it in the Editor panel. 

You can customize the [project sidebar](https://meta.stoplight.io/docs/platform/ZG9jOjIxOTkxNTkz-project-sidebar) to:

- Customize the order of files
- Override the title of files
- Selectively expose or hide files

## Project Toolbar

**Project Options**: Select the hamburger menu to work with these options:

* **Back to Workspace**: Leaves edit mode and returns you to the workspace home.
* **Preferences**: 
  - Autosave
  - Show empty directories
  - Theme (dark, light, or the default set in Workspace settings)
* **Git**:
  - Auto-pull 
  - Auto-translate SSH URLs
  <!-- https://github.com/stoplightio/platform-docs/issues/159 created to better document Git settings at a later time -->
* **Reclone Project**
* **Download Project ZIP**

<!-- focus: center -->
![Project Options](https://stoplight.io/api/v1/projects/cHJqOjI/images/9G0GkYCxwa8)

**Search**: Find anything in your project files. 

**Add to Project**: Use to add new assets to your project. This includes APIs, endpoints, models, articles, style guides, images, table of contents, files and directories. You can also import files and import directories and add a [Stoplight Config file](https://meta.stoplight.io/docs/platform/ZG9jOjE4ODEyNA-configure-projects) to your project. 

**Project Actions** (Changes depending on your state and the type of project):
  - **Back to workspace**: Returns you to the published view for the project.
  - **Publish**: When the project is not connected to a repository, shows when at least one change has been made in the project. 
  - **Commit and Publish**: When the project is connection to a repository, shows when at least one change has been made in the project.  
  - **Discard**: Once changes are made to a project, select the down arrow to discard them. 
  > For web project, discarding impacts unpublished changes made by all users and not just the user performing the discard.

**Project Name**: Shows the name of the current project. The version is shown for Stoplight projects. For projects connected to a repository, the name of the burrent branch is shown. Select the down arrow to pull changes into your project or to switch branches. 

## Editor Panel

Use the main editor panel to design APIs, write supporting documentation, and update style guides. 

Choose different views:
 - **Form**: Offers an intiutive editor for APIs, endpoints, and models. 
 - **Code**: Enables the code view for applicable files (not available for style guides).
 - **Preview**: Provides a preview of what the selected file will look like when it is published. For API operations, the [Try It](http-endpoints.md) feature is available in Preview mode. 

 **Validation and Linting** displays issues related to your API Specification using [style guide rules](../2a.-style-guides/a.style-guide-projects.md) and powered by [Spectral](https://meta.stoplight.io/docs/spectral/ZG9jOjYx-overview). Select to expand window and view error and warning details and locations.

A **Secondary Panel** is available on larger screens (width > 1400px). Switch between view types via the view toggle in the top right of the panel.