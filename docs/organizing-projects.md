# Creating & Organizing Projects


Within Workspaces, the most important concept in Stoplight is "Projects". Projects are a place for you to manage APIs, articles, and any other files that you want to store together. 

Projects can be a mixture of source code, API descriptions like OpenAPI and JSON Schema, and Markdown articles. Stoplight will analyze the API and Markdown, and leave your source code alone, so feel free to bundle them together if you want. We think it's much easier to keep track of documentation when it lives with the code, but it's certainly not required. 

Projects can be [created from Git](#TODO) if a workspace has been configured with Git providers. Alternatively, projects can be [created via Studio](TODO), or published from any filesystem structure using the [Stoplight CLI](#TODO).

## Import from Repositories

The quickest way to get projects into Stoplight is to pull them in from Git, and this can be done in Explorer. 

<!-- TODO Image of explorer add project from repositories -->

If the repository has Markdown articles, or API descriptions, then you will see them show up once the analyzer is finished running. If not, you can start to create this content in your file system, by using Studio to create a new API, or Markdown content.

## Brand New Projects

Using the [Studio module]() you can create and edit the contents of your projects, and push changes back to the Git repository when you're done. 

If you are starting a brand new project and there is nothing: no code, no API descriptions, and no documentation, this might be where you start, so you can get the full benefits of [API design-first](https://stoplight.io/api-design-guide/).

## Organizing Projects

Who controls what projects, how many APIs go in a repo, etc. are all decisions that need to be made within your organization. Stoplight has no bias towards a "monorepo" or a "multirepo" approach, it supports either. 

If you are using a "monorepo" approach, you might have one project, with a directory for each API, and contain the source code and API description inside that directory.

If you are using a "multirepo" approach, you might have one project for each API, and contain the source code and API description inside each project in any directory structure you like.

You could use a mixture of both, where multiple repositories exist, but there are a couple of APIs in there. Maybe one project known as the "Locations Service" has a "Public API" and an "Admin API" for managing it.

## Projects without Git

Git is very popular, but not used by everyone. If a different version control system is in use like Mercurial, SVN, SourceSafe, Bazaar, or your team uses another way to keep all their work organized, Stoplight has you covered.

[Stoplight CLI](#TODO Publishing via CLI) is a command-line tool, built as a NPM module, which can publish changes to Stoplight, and have them show up in Explorer just like any other project. They won't be editable in Studio, but the content will be available to read, search, etc like anything else. 
